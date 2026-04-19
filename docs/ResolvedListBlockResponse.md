
# ResolvedListBlockResponse


## Properties

Name | Type
------------ | -------------
`block_id` | string
`title` | string
`type` | string
`items` | [Array&lt;ResolvedListBlockResponseItemsInner&gt;](ResolvedListBlockResponseItemsInner.md)
`total_count` | number

## Example

```typescript
import type { ResolvedListBlockResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "block_id": null,
  "title": null,
  "type": null,
  "items": null,
  "total_count": null,
} satisfies ResolvedListBlockResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResolvedListBlockResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


