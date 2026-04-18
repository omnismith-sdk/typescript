
# RegisterPushDeviceRequest


## Properties

Name | Type
------------ | -------------
`token` | string
`device_name` | string

## Example

```typescript
import type { RegisterPushDeviceRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "token": null,
  "device_name": Pixel 9 Pro,
} satisfies RegisterPushDeviceRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as RegisterPushDeviceRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


