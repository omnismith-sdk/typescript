
# EntityRulePredicateOverviewResponse

Predicate condition or constraint evaluating an entity attribute.

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`attribute_slug` | string
`operator` | string
`value` | [EntityRulePredicateOverviewResponseValue](EntityRulePredicateOverviewResponseValue.md)

## Example

```typescript
import type { EntityRulePredicateOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "attribute_slug": status,
  "operator": eq,
  "value": null,
} satisfies EntityRulePredicateOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityRulePredicateOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


