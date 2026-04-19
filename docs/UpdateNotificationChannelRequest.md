
# UpdateNotificationChannelRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`credentials` | [UpdateNotificationChannelRequestCredentials](UpdateNotificationChannelRequestCredentials.md)

## Example

```typescript
import type { UpdateNotificationChannelRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Updated Bot Name,
  "credentials": null,
} satisfies UpdateNotificationChannelRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateNotificationChannelRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


