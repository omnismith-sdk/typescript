
# PushDeviceResponse


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
  "id": null,
  "token": null,
  "device_name": null,
  "created_at": null,
  "updated_at": null,
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


