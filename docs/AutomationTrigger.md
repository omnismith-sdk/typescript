
# AutomationTrigger

When the automation fires. Conditions are then checked on the record, and the actions run if they all hold.  **Record events.** `on_entity_created`, `on_entity_updated`, `on_attribute_changed` (needs `attributeId`) and `on_action_executed` (needs `actionId`, fires whenever that entity action runs). They never fire for writes made by an automation.  **Schedule.** `{\"type\": \"schedule\", \"cron\": \"<5-field cron>\", \"timezone\": \"<IANA timezone>\", \"templateId\": \"<optional template id>\"}`. - Without `templateId` each run executes the actions once, with no record: `{entity.*}` and `{values.*}` render empty, and the automation takes no conditions. - With `templateId` each run executes the actions once for every record of the template the conditions hold for, each record subject to the cooldown. A run that would match more than 500 records runs nothing and is recorded as one failed execution; narrow the conditions. - Conditions use `mode: \"current\"` only: a scheduled moment has no previous value. - Slots are read in `timezone`, so `0 9 * * *` stays at 09:00 local time across daylight-saving changes. Runs must be at least 5 minutes apart. A slot missed while the service was down runs once, late; several missed slots collapse into one run. `{timestamp}` is the slot the run was due at, and the automation\'s `nextRunAt` shows the next slot. - Example, every weekday at 09:00 Berlin time for every open ticket: `{\"type\": \"schedule\", \"cron\": \"0 9 * * 1-5\", \"timezone\": \"Europe/Berlin\", \"templateId\": \"<ticket template id>\"}` with the condition `{\"attributeId\": \"<status id>\", \"operator\": \"eq\", \"value\": \"<Open item id>\", \"mode\": \"current\"}`.  **Date reached.** `{\"type\": \"date_reached\", \"templateId\": \"<template id>\", \"attributeId\": \"<date or datetime attribute id>\", \"offsetMinutes\": <signed minutes>, \"timezone\": \"<IANA timezone>\"}`. Fires once per record when the record\'s date plus the offset is reached: deadlines, renewals, expirations, next-contact dates. - A date-only value is local midnight in `timezone`; a datetime is taken as stored (without an offset, as UTC). The offset is applied on the local calendar, whole days first: `-42660` (−30 days + 9 hours) is 09:00 local time thirty days before the date, `-60` is an hour before a datetime, `0` is the moment itself. - Every record with a date is scheduled when the automation is saved or enabled; afterwards each write that sets, changes or clears the date moves or cancels that record\'s run. A due time already in the past is never scheduled, so setting a past date does not fire. A deleted record fires nothing. - When the moment comes the conditions are checked on the record as it is then (`mode: \"current\"` only), and the cooldown applies. `{timestamp}` is the due time. - Writes made by an automation schedule other automations\' runs like any other write (a contract created by one automation gets its renewal reminder from another), but never the writing automation\'s own: if an automation changes the date it is watching, its pending run is dropped and not rescheduled, so it cannot loop on itself. - Example, renewal reminder at 09:00 Berlin time thirty days before `renewal_date`: `{\"type\": \"date_reached\", \"templateId\": \"<contract template id>\", \"attributeId\": \"<renewal_date id>\", \"offsetMinutes\": -42660, \"timezone\": \"Europe/Berlin\"}`. Pending runs are listed by `GET /automation/timers?automation_id=`.  **No change within.** `{\"type\": \"no_change_within\", \"templateId\": \"<template id>\", \"attributeId\": \"<watched attribute id>\", \"delayMinutes\": <minutes>}`. Fires once for a record when the watched attribute has not changed for `delayMinutes` while the conditions held: follow-ups, SLAs, escalations. - Omit `attributeId` to watch the record itself, i.e. its `updated_at`: then every write to the record restarts the clock, even one that leaves its values as they were. This is the heartbeat monitor: a device or job that reports by writing its record every few minutes, and an automation that fires when the writes stop. Metric points sent through `POST /entities/{id}/metrics` do not write the record. - The clock starts when a record is created and restarts whenever the watched attribute changes, but only while the conditions hold for the record. A write after which they no longer hold stops the clock. When the delay is over the conditions are checked once more on the record as it is then (`mode: \"current\"` only), and the cooldown applies. `{timestamp}` is the moment the delay ran out. - Records that already exist when the automation is saved are not clocked; their clock starts with their next write. Changing the trigger or the conditions of the automation (or disabling it) stops every running clock; editing its name, actions or cooldown does not. - Writes made by an automation start, restart and stop other automations\' clocks like any other write, but never the writing automation\'s own, so an escalation that sets `escalated_at` can start a second automation\'s clock without looping on itself. - Example, a ticket still New 24 hours after it was created: attribute `status`, condition `{\"attributeId\": \"<status id>\", \"operator\": \"eq\", \"value\": \"<New item id>\", \"mode\": \"current\"}`, `\"delayMinutes\": 1440`. - Example, no reply within 2 hours: attribute `replied_at`, condition `{\"attributeId\": \"<replied_at id>\", \"operator\": \"is_empty\", \"mode\": \"current\"}`, `\"delayMinutes\": 120`. - Example, a server silent for 15 minutes: `{\"type\": \"no_change_within\", \"templateId\": \"<server template id>\", \"delayMinutes\": 15}` with no `attributeId`, and the server\'s agent updating its record (e.g. its `status`) on every check.

## Properties

Name | Type
------------ | -------------
`type` | string
`templateId` | string
`attributeId` | string
`actionId` | string
`cron` | string
`timezone` | string
`delayMinutes` | number
`offsetMinutes` | number

## Example

```typescript
import type { AutomationTrigger } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "type": schedule,
  "templateId": 01912ecb-4654-7890-a1b2-c3d4e5f60088,
  "attributeId": 01912ecb-4654-7890-a1b2-c3d4e5f60077,
  "actionId": 01a09900-0000-7000-8000-000000000001,
  "cron": 0 9 * * 1-5,
  "timezone": Europe/Berlin,
  "delayMinutes": 1440,
  "offsetMinutes": -42660,
} satisfies AutomationTrigger

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationTrigger
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


