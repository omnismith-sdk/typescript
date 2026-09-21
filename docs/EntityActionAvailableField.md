
# EntityActionAvailableField

One value the action asks for, resolved to the attribute it writes. Send it under `values` keyed by `slug` (or `attribute_id`).

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`slug` | string
`name` | string
`attribute_type` | number
`data_type` | number
`required` | boolean
`hint` | string
`list_items` | [Array&lt;EntityActionAvailableFieldListItemsInner&gt;](EntityActionAvailableFieldListItemsInner.md)
`reference_config` | [EntityActionAvailableFieldReferenceConfig](EntityActionAvailableFieldReferenceConfig.md)

## Example

```typescript
import type { EntityActionAvailableField } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "slug": attendee_count,
  "name": Attendee count,
  "attribute_type": 0,
  "data_type": 1,
  "required": true,
  "hint": How many guests will attend,
  "list_items": null,
  "reference_config": null,
} satisfies EntityActionAvailableField

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionAvailableField
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


