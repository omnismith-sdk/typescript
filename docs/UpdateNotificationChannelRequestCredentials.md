
# UpdateNotificationChannelRequestCredentials

Updated type-specific credentials payload (e.g. `bot_token` for Telegram; `url`, `auth_type`, `token`, `username`, `password`, `headers` for webhook)

## Properties

Name | Type
------------ | -------------
`bot_token` | string
`url` | string
`auth_type` | string
`token` | string
`username` | string
`password` | string
`headers` | { [key: string]: string; }

## Example

```typescript
import type { UpdateNotificationChannelRequestCredentials } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "bot_token": 654321:NEW-TOKEN...,
  "url": https://api.example.com/updated-webhook,
  "auth_type": bearer,
  "token": omni_live_secret_key_updated,
  "username": new_user,
  "password": new_secret,
  "headers": null,
} satisfies UpdateNotificationChannelRequestCredentials

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateNotificationChannelRequestCredentials
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


