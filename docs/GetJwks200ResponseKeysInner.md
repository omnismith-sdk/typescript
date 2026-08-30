
# GetJwks200ResponseKeysInner


## Properties

Name | Type
------------ | -------------
`kty` | string
`use` | string
`alg` | string
`kid` | string
`n` | string
`e` | string

## Example

```typescript
import type { GetJwks200ResponseKeysInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "kty": RSA,
  "use": sig,
  "alg": RS256,
  "kid": a1b2c3d4e5f67890,
  "n": u1l2m3n4o5p6...,
  "e": AQAB,
} satisfies GetJwks200ResponseKeysInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetJwks200ResponseKeysInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


