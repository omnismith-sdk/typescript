
# CreateDashboardBlockRequestConfigAggregationsInner


## Properties

Name | Type
------------ | -------------
`op` | string
`field` | string

## Example

```typescript
import type { CreateDashboardBlockRequestConfigAggregationsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "op": sum,
  "field": mrr,
} satisfies CreateDashboardBlockRequestConfigAggregationsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateDashboardBlockRequestConfigAggregationsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


