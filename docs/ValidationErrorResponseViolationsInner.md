
# ValidationErrorResponseViolationsInner


## Properties

Name | Type
------------ | -------------
`field` | string
`message` | string
`rule` | [ValidationErrorResponseViolationsInnerRule](ValidationErrorResponseViolationsInnerRule.md)

## Example

```typescript
import type { ValidationErrorResponseViolationsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "field": attributes.dietary_options,
  "message": Dietary options are required when dietary is yes,
  "rule": null,
} satisfies ValidationErrorResponseViolationsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ValidationErrorResponseViolationsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


