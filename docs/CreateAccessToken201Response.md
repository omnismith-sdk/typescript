
# CreateAccessToken201Response


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`api_key` | string
`expires_at` | Date
`created_at` | Date

## Example

```typescript
import type { CreateAccessToken201Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 0192a543-7f28-72b1-9b7e-97c997321034,
  "name": CI/CD Deployment Key,
  "api_key": omni_live_secret_key_9f83b27c1a4e6d80,
  "expires_at": 2026-12-31T23:59:59Z,
  "created_at": 2026-08-26T12:00Z,
} satisfies CreateAccessToken201Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAccessToken201Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


