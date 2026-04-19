
# SessionResponse

Login session details

## Properties

Name | Type
------------ | -------------
`id` | string
`user_id` | string
`email` | string
`role_id` | string
`ip_address` | string
`user_agent` | string
`created_at` | Date
`expires_at` | Date
`revoked_at` | Date
`revoked_by` | string
`revoked_reason` | string
`status` | string

## Example

```typescript
import type { SessionResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "user_id": null,
  "email": null,
  "role_id": null,
  "ip_address": 192.168.1.1,
  "user_agent": null,
  "created_at": null,
  "expires_at": null,
  "revoked_at": null,
  "revoked_by": null,
  "revoked_reason": null,
  "status": null,
} satisfies SessionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SessionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


