
# ApproveOAuthAuthorizationRequest

Submits user consent approval for an authorized OAuth client and the set of projects it may reach.

## Properties

Name | Type
------------ | -------------
`client_id` | string
`redirect_uri` | string
`project_ids` | Array&lt;string&gt;
`code_challenge` | string
`code_challenge_method` | string
`scopes` | Array&lt;string&gt;
`state` | string

## Example

```typescript
import type { ApproveOAuthAuthorizationRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "client_id": omni_client_0195a8f2c3e471238000000000000001,
  "redirect_uri": https://claude.ai/api/mcp/oauth_callback,
  "project_ids": ["0195a8f2-c3e4-7123-8000-000000000001"],
  "code_challenge": E9Melhoa2OwvFrGMTJguCH5SZXgk6uKUaz312M20O48,
  "code_challenge_method": S256,
  "scopes": ["omnismith:all"],
  "state": state_xyz123,
} satisfies ApproveOAuthAuthorizationRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ApproveOAuthAuthorizationRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


