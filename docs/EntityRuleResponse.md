
# EntityRuleResponse

A template-scoped business rule: when every `when` condition holds (an empty list always holds), every `then` constraint must hold or the write is rejected with 422.

## Properties

Name | Type
------------ | -------------
`id` | string
`template_id` | string
`name` | string
`message` | string
`is_enabled` | boolean
`when` | [Array&lt;EntityRulePredicate&gt;](EntityRulePredicate.md)
`then` | [Array&lt;EntityRulePredicate&gt;](EntityRulePredicate.md)
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { EntityRuleResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01a09800-0000-7000-8000-000000000001,
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "name": Dietary options when dietary,
  "message": Dietary options are required when dietary is yes,
  "is_enabled": true,
  "when": null,
  "then": null,
  "created_at": 2026-09-13T10:30Z,
  "updated_at": 2026-09-13T10:30Z,
} satisfies EntityRuleResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityRuleResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


