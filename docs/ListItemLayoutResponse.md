
# ListItemLayoutResponse

Display sorting rank for a choice option item in UI dropdowns.

## Properties

Name | Type
------------ | -------------
`list_item_id` | string
`attribute_id` | string
`sort_order` | number

## Example

```typescript
import type { ListItemLayoutResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "list_item_id": 019a6b2c-8c3a-7c2e-8b3f-6c8a1a2b3c4d,
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "sort_order": 0,
} satisfies ListItemLayoutResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ListItemLayoutResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


