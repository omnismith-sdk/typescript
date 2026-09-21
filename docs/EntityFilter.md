
# EntityFilter

One filter clause. The value shape follows the operator.

## Properties

Name | Type
------------ | -------------
`field` | string
`operator` | string
`value` | [EntityFilterValue](EntityFilterValue.md)

## Example

```typescript
import type { EntityFilter } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "field": price,
  "operator": gt,
  "value": null,
} satisfies EntityFilter

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityFilter
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


