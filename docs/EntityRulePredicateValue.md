
# EntityRulePredicateValue

Comparison value serialized as a string (list item UUID for list attributes, entity UUID for references, `true`/`false` for booleans). A list of list item UUIDs for `in`. Omitted for `is_empty` / `is_not_empty`.

## Properties

Name | Type
------------ | -------------

## Example

```typescript
import type { EntityRulePredicateValue } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
} satisfies EntityRulePredicateValue

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityRulePredicateValue
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


