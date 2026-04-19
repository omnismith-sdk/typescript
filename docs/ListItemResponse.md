
# ListItemResponse


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
  "id": null,
  "attribute_id": null,
  "value": null,
  "sort_order": null,
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


