
# AggregateEntitiesRequest

Which records to reduce, how to group them, and which reduces to compute per group.

## Properties

Name | Type
------------ | -------------
`filter_groups` | Array&lt;Array&lt;EntityFilter&gt;&gt;
`group_by` | Array&lt;string&gt;
`aggregations` | [Array&lt;AggregateEntitiesRequestAggregationsInner&gt;](AggregateEntitiesRequestAggregationsInner.md)
`limit` | number

## Example

```typescript
import type { AggregateEntitiesRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "filter_groups": [[{"field":"status","operator":"eq","value":"018b2f1b-8c1a-75b3-8000-7f0000010020"}]],
  "group_by": ["tier","country"],
  "aggregations": [{"op":"count"},{"op":"sum","field":"mrr"}],
  "limit": 50,
} satisfies AggregateEntitiesRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AggregateEntitiesRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


