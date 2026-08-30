
# RegisterUserRequest

Payload for registering a new user

## Properties

Name | Type
------------ | -------------
`email` | string
`password` | string
`captchaToken` | string

## Example

```typescript
import type { RegisterUserRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "email": user@example.com,
  "password": securePassword123,
  "captchaToken": 0.XT2...gX,
} satisfies RegisterUserRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RegisterUserRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


