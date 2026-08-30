
# GetOAuthAuthorizeInfo200ResponseProjectsInner


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`is_owner` | boolean
`role_name` | string

## Example

```typescript
import type { GetOAuthAuthorizeInfo200ResponseProjectsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 0195a8f2-c3e4-7123-8000-000000000001,
  "name": Production Analytics,
  "is_owner": true,
  "role_name": Owner,
} satisfies GetOAuthAuthorizeInfo200ResponseProjectsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetOAuthAuthorizeInfo200ResponseProjectsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


