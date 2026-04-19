
# CreateNotificationChannelRequest


## Properties

Name | Type
------------ | -------------
`type` | string
`name` | string
`credentials` | [CreateNotificationChannelRequestCredentials](CreateNotificationChannelRequestCredentials.md)

## Example

```typescript
import type { CreateNotificationChannelRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "type": telegram,
  "name": Alerts Bot,
  "credentials": null,
} satisfies CreateNotificationChannelRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateNotificationChannelRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


