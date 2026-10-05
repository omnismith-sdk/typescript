
# UpdateNotificationChannelRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`credentials` | [UpdateNotificationChannelRequestCredentials](UpdateNotificationChannelRequestCredentials.md)
`rate_limit_per_minute` | number

## Example

```typescript
import type { UpdateNotificationChannelRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Updated Alerts Bot,
  "credentials": null,
  "rate_limit_per_minute": 20,
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


