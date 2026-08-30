
# CreateAccessTokenRequest

Payload for generating a new programmatic API access token

## Properties

Name | Type
------------ | -------------
`name` | string
`expires_at` | Date

## Example

```typescript
import type { CreateAccessTokenRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": CI/CD Deployment Key,
  "expires_at": 2026-12-31T23:59:59Z,
} satisfies CreateAccessTokenRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAccessTokenRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


