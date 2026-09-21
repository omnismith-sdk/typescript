
# EntityActionResponse

A named, template-scoped operation on one record: a precondition that gates it, the fields the operator is asked for, and presets applied silently. Executing an action is one entity write that passes the template\'s rules like any other. A status transition is `precondition: [status eq draft]`, `presets: [status = confirmed]`.

## Properties

Name | Type
------------ | -------------
`id` | string
`template_id` | string
`slug` | string
`name` | string
`description` | string
`icon` | string
`is_enabled` | boolean
`precondition` | [Array&lt;EntityRulePredicate&gt;](EntityRulePredicate.md)
`fields` | [Array&lt;EntityActionField&gt;](EntityActionField.md)
`presets` | [Array&lt;EntityActionPreset&gt;](EntityActionPreset.md)
`sort_order` | number
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { EntityActionResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01a09900-0000-7000-8000-000000000001,
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "slug": confirm_attendance,
  "name": Confirm attendance,
  "description": Marks the guest as confirmed and records the party size,
  "icon": check_circle,
  "is_enabled": true,
  "precondition": null,
  "fields": null,
  "presets": null,
  "sort_order": 0,
  "created_at": 2026-09-13T10:30Z,
  "updated_at": 2026-09-13T10:30Z,
} satisfies EntityActionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


