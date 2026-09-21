
# EntityAttributesInputValueAnyOf1

Operation object: apply an atomic operation to the stored value instead of overwriting it. Number attributes and metrics only; a never-set value counts as 0.

## Properties

Name | Type
------------ | -------------
`op` | string
`value` | number

## Example

```typescript
import type { EntityAttributesInputValueAnyOf1 } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "op": null,
  "value": 1,
} satisfies EntityAttributesInputValueAnyOf1

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityAttributesInputValueAnyOf1
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


