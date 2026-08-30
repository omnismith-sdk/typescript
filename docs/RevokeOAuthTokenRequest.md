
# RevokeOAuthTokenRequest

OAuth 2.0 token revocation request (RFC 7009) to invalidate active refresh or access tokens.

## Properties

Name | Type
------------ | -------------
`token` | string
`token_type_hint` | string
`client_id` | string

## Example

```typescript
import type { RevokeOAuthTokenRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "token": omni_ort_0195a8f2c3e471238000000000000004,
  "token_type_hint": refresh_token,
  "client_id": omni_client_0195a8f2c3e471238000000000000001,
} satisfies RevokeOAuthTokenRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RevokeOAuthTokenRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


