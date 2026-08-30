
# SemanticSearchResultItem

Entity search match ranked by cosine similarity score

## Properties

Name | Type
------------ | -------------
`entity` | [EntityResponse](EntityResponse.md)
`similarity_score` | number

## Example

```typescript
import type { SemanticSearchResultItem } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "entity": null,
  "similarity_score": 0.892,
} satisfies SemanticSearchResultItem

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SemanticSearchResultItem
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


