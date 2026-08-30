
# GetOAuthAuthorizeInfo200Response


## Properties

Name | Type
------------ | -------------
`client_id` | string
`client_name` | string
`redirect_uri` | string
`scopes` | Array&lt;string&gt;
`user_email` | string
`active_project_id` | string
`projects` | [Array&lt;GetOAuthAuthorizeInfo200ResponseProjectsInner&gt;](GetOAuthAuthorizeInfo200ResponseProjectsInner.md)
`state` | string

## Example

```typescript
import type { GetOAuthAuthorizeInfo200Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "client_id": omni_client_0195a8f2c3e471238000000000000001,
  "client_name": Claude Desktop,
  "redirect_uri": https://claude.ai/api/mcp/oauth_callback,
  "scopes": ["omnismith:all"],
  "user_email": demo@omnismith.io,
  "active_project_id": 0195a8f2-c3e4-7123-8000-000000000001,
  "projects": null,
  "state": state_xyz123,
} satisfies GetOAuthAuthorizeInfo200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetOAuthAuthorizeInfo200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


