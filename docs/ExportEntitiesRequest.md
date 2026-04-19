
# ExportEntitiesRequest


## Properties

Name | Type
------------ | -------------
`global_search` | string
`filters` | [Array&lt;ExportEntitiesRequestFiltersInner&gt;](ExportEntitiesRequestFiltersInner.md)

## Example

```typescript
import type { ExportEntitiesRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "global_search": null,
  "filters": null,
} satisfies ExportEntitiesRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExportEntitiesRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


