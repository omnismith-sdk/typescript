
# CreateSavedQueryRequest


## Properties

Name | Type
------------ | -------------
`template_id` | string
`name` | string
`global_search` | string
`filters` | [Array&lt;CreateSavedQueryRequestFiltersInner&gt;](CreateSavedQueryRequestFiltersInner.md)

## Example

```typescript
import type { CreateSavedQueryRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": null,
  "name": null,
  "global_search": null,
  "filters": null,
} satisfies CreateSavedQueryRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateSavedQueryRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


