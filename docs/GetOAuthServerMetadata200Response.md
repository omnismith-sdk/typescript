
# GetOAuthServerMetadata200Response


## Properties

Name | Type
------------ | -------------
`issuer` | string
`authorization_endpoint` | string
`token_endpoint` | string
`registration_endpoint` | string
`revocation_endpoint` | string
`jwks_uri` | string
`response_types_supported` | Array&lt;string&gt;
`grant_types_supported` | Array&lt;string&gt;
`code_challenge_methods_supported` | Array&lt;string&gt;
`scopes_supported` | Array&lt;string&gt;
`token_endpoint_auth_methods_supported` | Array&lt;string&gt;
`service_documentation` | string
`client_uri` | string
`logo_uri` | string

## Example

```typescript
import type { GetOAuthServerMetadata200Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "issuer": https://api.omnismith.io,
  "authorization_endpoint": https://app.omnismith.io/oauth/authorize,
  "token_endpoint": https://api.omnismith.io/oauth/token,
  "registration_endpoint": https://api.omnismith.io/oauth/register,
  "revocation_endpoint": https://api.omnismith.io/oauth/revoke,
  "jwks_uri": https://api.omnismith.io/.well-known/jwks.json,
  "response_types_supported": ["code"],
  "grant_types_supported": ["authorization_code","refresh_token"],
  "code_challenge_methods_supported": ["S256","plain"],
  "scopes_supported": ["omnismith:all","omnismith:read","omnismith:write"],
  "token_endpoint_auth_methods_supported": ["none","client_secret_post"],
  "service_documentation": https://docs.omnismith.io,
  "client_uri": https://omnismith.io,
  "logo_uri": https://omnismith.io/logo.png,
} satisfies GetOAuthServerMetadata200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetOAuthServerMetadata200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


