
# ScopeAccessInput


## Properties

Name | Type
------------ | -------------
`template_id` | string
`conditions` | [Array&lt;ScopeConditionInput&gt;](ScopeConditionInput.md)

## Example

```typescript
import type { ScopeAccessInput } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": null,
  "conditions": null,
} satisfies ScopeAccessInput

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ScopeAccessInput
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


