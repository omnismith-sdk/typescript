
# CreateInboundEndpointRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`signature` | { [key: string]: any; }
`mapping` | { [key: string]: any; }
`enabled` | boolean
`secret` | string
`delivery_id_source` | [InboundDeliveryIdSource](InboundDeliveryIdSource.md)

## Example

```typescript
import type { CreateInboundEndpointRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Stripe customers,
  "signature": null,
  "mapping": null,
  "enabled": null,
  "secret": whsec_dummy_secret_value,
  "delivery_id_source": null,
} satisfies CreateInboundEndpointRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateInboundEndpointRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


