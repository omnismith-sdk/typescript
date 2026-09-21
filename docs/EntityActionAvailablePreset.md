
# EntityActionAvailablePreset

A value the action writes silently; shown so the operator knows what will change.

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`slug` | string
`name` | string
`value` | string
`display_value` | string

## Example

```typescript
import type { EntityActionAvailablePreset } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "slug": status,
  "name": Status,
  "value": 018b2f1b-8c1a-75b3-8000-7f0000010020,
  "display_value": Confirmed,
} satisfies EntityActionAvailablePreset

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionAvailablePreset
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


