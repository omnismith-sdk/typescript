
# SemanticSearchEntitiesRequest

Embedding vector and parameters for semantic similarity search

## Properties

Name | Type
------------ | -------------
`query_vector` | Array&lt;number&gt;
`template_id` | string
`limit` | number
`threshold` | number
`verbose` | boolean

## Example

```typescript
import type { SemanticSearchEntitiesRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "query_vector": [0.0123,-0.0456,0.0789,0.0012],
  "template_id": product_catalog,
  "limit": 10,
  "threshold": 0.75,
  "verbose": false,
} satisfies SemanticSearchEntitiesRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SemanticSearchEntitiesRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


