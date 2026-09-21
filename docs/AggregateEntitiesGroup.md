
# AggregateEntitiesGroup

One group of records: its key (one entry per group_by field, in request order) and the reduces computed over it (one entry per aggregation, in request order).

## Properties

Name | Type
------------ | -------------
`key` | [Array&lt;AggregateEntitiesGroupKeyInner&gt;](AggregateEntitiesGroupKeyInner.md)
`aggregates` | [Array&lt;AggregateEntitiesGroupAggregatesInner&gt;](AggregateEntitiesGroupAggregatesInner.md)

## Example

```typescript
import type { AggregateEntitiesGroup } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "key": null,
  "aggregates": null,
} satisfies AggregateEntitiesGroup

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AggregateEntitiesGroup
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


