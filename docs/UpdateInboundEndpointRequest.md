
# UpdateInboundEndpointRequest

Send at least one field. Omitted fields keep their value.

## Properties

Name | Type
------------ | -------------
`name` | string
`enabled` | boolean
`signature` | { [key: string]: any; }
`mapping` | { [key: string]: any; }
`delivery_id_source` | [InboundDeliveryIdSource](InboundDeliveryIdSource.md)

## Example

```typescript
import type { UpdateInboundEndpointRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Stripe customers,
  "enabled": null,
  "signature": null,
  "mapping": null,
  "delivery_id_source": null,
} satisfies UpdateInboundEndpointRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateInboundEndpointRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


