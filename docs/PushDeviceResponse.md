
# PushDeviceResponse

Registered mobile push notification device token record

## Properties

Name | Type
------------ | -------------
`id` | string
`token` | string
`device_name` | string
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { PushDeviceResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01912ecb-4654-7890-a1b2-c3d4e5f60005,
  "token": fcm_token_...abc123,
  "device_name": Pixel 9 Pro,
  "created_at": 2026-08-26T12:00Z,
  "updated_at": 2026-08-26T12:00Z,
} satisfies PushDeviceResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PushDeviceResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


