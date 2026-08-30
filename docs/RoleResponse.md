
# RoleResponse

Metadata describing a system or custom user role

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`is_owner` | boolean
`created_at` | Date

## Example

```typescript
import type { RoleResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  "name": Data Analyst,
  "is_owner": false,
  "created_at": 2026-08-26T12:00Z,
} satisfies RoleResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RoleResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


