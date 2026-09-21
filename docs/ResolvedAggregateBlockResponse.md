
# ResolvedAggregateBlockResponse

Computed result for an aggregate block: entities matching the template and filters, grouped and reduced per group

## Properties

Name | Type
------------ | -------------
`block_id` | string
`title` | string
`type` | string
`limit` | number
`truncated` | boolean
`groups` | [Array&lt;ResolvedAggregateBlockResponseGroupsInner&gt;](ResolvedAggregateBlockResponseGroupsInner.md)

## Example

```typescript
import type { ResolvedAggregateBlockResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "block_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  "title": Deals by Stage,
  "type": aggregate,
  "limit": 50,
  "truncated": false,
  "groups": null,
} satisfies ResolvedAggregateBlockResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResolvedAggregateBlockResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


