
# ListItemResponse

Selectable choice option item for a List-type attribute.

## Properties

Name | Type
------------ | -------------
`id` | string
`attribute_id` | string
`value` | string
`sort_order` | number

## Example

```typescript
import type { ListItemResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 019a6b2c-8c3a-7c2e-8b3f-6c8a1a2b3c4d,
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "value": Red,
  "sort_order": 0,
} satisfies ListItemResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListItemResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


