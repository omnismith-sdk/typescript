
# RoleEntityScopeResponse

Filter-based entity access scope defining row-level permissions for a role under a template

## Properties

Name | Type
------------ | -------------
`template_id` | string
`conditions` | [Array&lt;RoleEntityScopeConditionResponse&gt;](RoleEntityScopeConditionResponse.md)

## Example

```typescript
import type { RoleEntityScopeResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  "conditions": null,
} satisfies RoleEntityScopeResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RoleEntityScopeResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


