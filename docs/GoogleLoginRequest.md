
# GoogleLoginRequest

Payload for Google Sign-In authentication

## Properties

Name | Type
------------ | -------------
`credential` | string

## Example

```typescript
import type { GoogleLoginRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "credential": eyJhbGciOiJSUzI1NiIs...,
} satisfies GoogleLoginRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GoogleLoginRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


