
# RoleEntityScopeConditionResponse

Individual attribute filter condition for row-level access control

## Properties

Name | Type
------------ | -------------
`field` | string
`operator` | string
`value` | string

## Example

```typescript
import type { RoleEntityScopeConditionResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "field": 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7b,
  "operator": eq,
  "value": active,
} satisfies RoleEntityScopeConditionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RoleEntityScopeConditionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


