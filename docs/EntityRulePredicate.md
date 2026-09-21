
# EntityRulePredicate

One predicate over an attribute\'s current value. Used both as a `when` condition and as a `then` constraint.

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`operator` | string
`value` | [EntityRulePredicateValue](EntityRulePredicateValue.md)

## Example

```typescript
import type { EntityRulePredicate } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "operator": eq,
  "value": null,
} satisfies EntityRulePredicate

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityRulePredicate
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


