
# RegisterOAuthClientRequest

Dynamic Client Registration request parameters (RFC 7591) for provisioning an OAuth 2.1 client.

## Properties

Name | Type
------------ | -------------
`client_name` | string
`redirect_uris` | Array&lt;string&gt;
`grant_types` | Array&lt;string&gt;
`response_types` | Array&lt;string&gt;
`token_endpoint_auth_method` | string

## Example

```typescript
import type { RegisterOAuthClientRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "client_name": Claude Desktop,
  "redirect_uris": ["https://claude.ai/api/mcp/oauth_callback","https://oauth.pstmn.io/v1/callback"],
  "grant_types": ["authorization_code","refresh_token"],
  "response_types": ["code"],
  "token_endpoint_auth_method": none,
} satisfies RegisterOAuthClientRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RegisterOAuthClientRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


