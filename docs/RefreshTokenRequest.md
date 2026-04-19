
# RefreshTokenRequest

Payload for refreshing an access token

## Properties

Name | Type
------------ | -------------
`refresh_token` | string

## Example

```typescript
import type { RefreshTokenRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "refresh_token": dGhpcyBpcyBhIHNhbXBsZSByZWZyZXNoIHRva2VuIGJhc2U2NA,
} satisfies RefreshTokenRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RefreshTokenRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


