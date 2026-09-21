
# SessionResponse

Detailed metadata describing a user login session and token status

## Properties

Name | Type
------------ | -------------
`id` | string
`user_id` | string
`email` | string
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
  "id": 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
  "user_id": 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7b,
  "email": demo@omnismith.io,
  "ip_address": 192.168.1.1,
  "user_agent": Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7),
  "created_at": 2026-08-26T12:00Z,
  "expires_at": 2026-09-26T12:00Z,
  "revoked_at": null,
  "revoked_by": null,
  "revoked_reason": null,
  "status": active,
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


