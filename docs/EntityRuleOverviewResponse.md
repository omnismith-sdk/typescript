
# EntityRuleOverviewResponse

Template-scoped validation rule. All writes must satisfy active rules.

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`message` | string
`is_enabled` | boolean
`when` | [Array&lt;EntityRulePredicateOverviewResponse&gt;](EntityRulePredicateOverviewResponse.md)
`then` | [Array&lt;EntityRulePredicateOverviewResponse&gt;](EntityRulePredicateOverviewResponse.md)

## Example

```typescript
import type { EntityRuleOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01a09800-0000-7000-8000-000000000001,
  "name": Status transition check,
  "message": Status must be verified,
  "is_enabled": true,
  "when": null,
  "then": null,
} satisfies EntityRuleOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityRuleOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


