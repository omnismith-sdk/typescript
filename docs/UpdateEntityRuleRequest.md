
# UpdateEntityRuleRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`message` | string
`when` | [Array&lt;EntityRulePredicate&gt;](EntityRulePredicate.md)
`then` | [Array&lt;EntityRulePredicate&gt;](EntityRulePredicate.md)

## Example

```typescript
import type { UpdateEntityRuleRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Dietary options when dietary,
  "message": Dietary options are required when dietary is yes,
  "when": null,
  "then": null,
} satisfies UpdateEntityRuleRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateEntityRuleRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


