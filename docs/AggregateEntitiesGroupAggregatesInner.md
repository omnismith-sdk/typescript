
# AggregateEntitiesGroupAggregatesInner


## Properties

Name | Type
------------ | -------------
`op` | string
`field` | string
`value` | [AggregateEntitiesGroupAggregatesInnerValue](AggregateEntitiesGroupAggregatesInnerValue.md)

## Example

```typescript
import type { AggregateEntitiesGroupAggregatesInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "op": sum,
  "field": mrr,
  "value": null,
} satisfies AggregateEntitiesGroupAggregatesInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AggregateEntitiesGroupAggregatesInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


