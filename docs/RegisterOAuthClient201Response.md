
# RegisterOAuthClient201Response


## Properties

Name | Type
------------ | -------------
`client_id` | string
`client_secret` | string
`client_name` | string
`redirect_uris` | Array&lt;string&gt;
`grant_types` | Array&lt;string&gt;
`response_types` | Array&lt;string&gt;
`token_endpoint_auth_method` | string
`client_id_issued_at` | number

## Example

```typescript
import type { RegisterOAuthClient201Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "client_id": omni_client_0195a8f2c3e471238000000000000001,
  "client_secret": omni_sec_0195a8f2c3e471238000000000000002,
  "client_name": Claude Desktop,
  "redirect_uris": ["https://claude.ai/api/mcp/oauth_callback"],
  "grant_types": ["authorization_code","refresh_token"],
  "response_types": ["code"],
  "token_endpoint_auth_method": none,
  "client_id_issued_at": 1724788800,
} satisfies RegisterOAuthClient201Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RegisterOAuthClient201Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


