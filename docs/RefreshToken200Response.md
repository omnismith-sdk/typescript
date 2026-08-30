
# RefreshToken200Response


## Properties

Name | Type
------------ | -------------
`access_token` | string
`expires_at` | number
`refresh_token` | string
`refresh_expires_at` | number

## Example

```typescript
import type { RefreshToken200Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "access_token": eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...,
  "expires_at": 1724688000,
  "refresh_token": dGhpcyBpcyBhIHNhbXBsZSByZWZyZXNoIHRva2Vu,
  "refresh_expires_at": 1727280000,
} satisfies RefreshToken200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RefreshToken200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


