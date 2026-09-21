
# AggregateEntitiesGroupKeyInner


## Properties

Name | Type
------------ | -------------
`field` | string
`value` | [AggregateEntitiesGroupKeyInnerValue](AggregateEntitiesGroupKeyInnerValue.md)
`custom_value` | string

## Example

```typescript
import type { AggregateEntitiesGroupKeyInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "field": tier,
  "value": null,
  "custom_value": Team,
} satisfies AggregateEntitiesGroupKeyInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AggregateEntitiesGroupKeyInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


