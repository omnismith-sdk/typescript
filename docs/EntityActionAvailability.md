
# EntityActionAvailability

An enabled action of the record\'s template, evaluated against the record: whether it can run now, and what it asks for and sets when it does.

## Properties

Name | Type
------------ | -------------
`id` | string
`slug` | string
`name` | string
`description` | string
`icon` | string
`available` | boolean
`unavailable_reason` | string
`fields` | [Array&lt;EntityActionAvailableField&gt;](EntityActionAvailableField.md)
`presets` | [Array&lt;EntityActionAvailablePreset&gt;](EntityActionAvailablePreset.md)

## Example

```typescript
import type { EntityActionAvailability } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01a09900-0000-7000-8000-000000000001,
  "slug": confirm_attendance,
  "name": Confirm attendance,
  "description": Marks the guest as confirmed and records the party size,
  "icon": check_circle,
  "available": false,
  "unavailable_reason": Status must be "Draft"; currently "Confirmed".,
  "fields": null,
  "presets": null,
} satisfies EntityActionAvailability

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionAvailability
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


