
# NotificationChannelResponse


## Properties

Name | Type
------------ | -------------
`id` | string
`type` | string
`name` | string
`credentials` | { [key: string]: string; }
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { NotificationChannelResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "type": null,
  "name": null,
  "credentials": null,
  "created_at": null,
  "updated_at": null,
} satisfies NotificationChannelResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as NotificationChannelResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


