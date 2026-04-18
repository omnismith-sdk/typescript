
# GoogleLogin200Response


## Properties

Name | Type
------------ | -------------
`access_token` | string
`expires_at` | number
`refresh_token` | string
`refresh_expires_at` | number

## Example

```typescript
import type { GoogleLogin200Response } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "access_token": null,
  "expires_at": null,
  "refresh_token": null,
  "refresh_expires_at": null,
} satisfies GoogleLogin200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GoogleLogin200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


