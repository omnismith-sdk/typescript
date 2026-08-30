
# ApproveOAuthAuthorization200Response


## Properties

Name | Type
------------ | -------------
`code` | string
`redirect_uri` | string
`callback_url` | string
`state` | string

## Example

```typescript
import type { ApproveOAuthAuthorization200Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "code": omni_code_0195a8f2c3e471238000000000000003,
  "redirect_uri": https://claude.ai/api/mcp/oauth_callback,
  "callback_url": https://claude.ai/api/mcp/oauth_callback?code=omni_code_0195a8f2c3e471238000000000000003&state=state_xyz123,
  "state": state_xyz123,
} satisfies ApproveOAuthAuthorization200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ApproveOAuthAuthorization200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


