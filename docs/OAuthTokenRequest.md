
# OAuthTokenRequest

OAuth 2.0 token grant request (RFC 6749 / RFC 7636) for authorization_code or refresh_token grant types.

## Properties

Name | Type
------------ | -------------
`grant_type` | string
`client_id` | string
`client_secret` | string
`code` | string
`redirect_uri` | string
`code_verifier` | string
`refresh_token` | string
`scope` | string

## Example

```typescript
import type { OAuthTokenRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "grant_type": authorization_code,
  "client_id": omni_client_0195a8f2c3e471238000000000000001,
  "client_secret": omni_sec_0195a8f2c3e471238000000000000002,
  "code": omni_code_0195a8f2c3e471238000000000000003,
  "redirect_uri": https://claude.ai/api/mcp/oauth_callback,
  "code_verifier": dBjftJeZ4CVP-mB92K27uhbUJU1p1r_wW1gFWFOEjXk,
  "refresh_token": omni_ort_0195a8f2c3e471238000000000000004,
  "scope": omnismith:all,
} satisfies OAuthTokenRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as OAuthTokenRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


