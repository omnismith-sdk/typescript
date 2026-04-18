
# AccessTokenResponse


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`expires_at` | Date
`created_at` | Date
`last_used_at` | Date

## Example

```typescript
import type { AccessTokenResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "expires_at": null,
  "created_at": null,
  "last_used_at": null,
} satisfies AccessTokenResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AccessTokenResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


