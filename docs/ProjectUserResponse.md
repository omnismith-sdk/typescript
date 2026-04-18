
# ProjectUserResponse

User in Project details

## Properties

Name | Type
------------ | -------------
`id` | string
`user_id` | string
`project_id` | string
`role_id` | string
`role_name` | string
`user_email` | string
`user_name` | string
`joined_at` | Date
`left_at` | Date

## Example

```typescript
import type { ProjectUserResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "user_id": null,
  "project_id": null,
  "role_id": null,
  "role_name": null,
  "user_email": null,
  "user_name": null,
  "joined_at": null,
  "left_at": null,
} satisfies ProjectUserResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectUserResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


