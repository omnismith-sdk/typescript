
# TestNotificationChannelRequest


## Properties

Name | Type
------------ | -------------
`chat_id` | string
`message` | string
`title` | string

## Example

```typescript
import type { TestNotificationChannelRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "chat_id": 123456789,
  "message": Test message from Omnismith,
  "title": null,
} satisfies TestNotificationChannelRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TestNotificationChannelRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


