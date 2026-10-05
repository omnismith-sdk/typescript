
# InboundEndpointResponse

A public URL through which one outside system writes records into one template. Secret values are only ever returned when a secret is issued.

## Properties

Name | Type
------------ | -------------
`id` | string
`template_id` | string
`name` | string
`enabled` | boolean
`url` | string
`signature` | { [key: string]: any; }
`mapping` | { [key: string]: any; }
`delivery_id_source` | [InboundDeliveryIdSource](InboundDeliveryIdSource.md)
`secrets` | [Array&lt;InboundSecret&gt;](InboundSecret.md)
`last_signature_failure_at` | Date
`created_by` | string
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { InboundEndpointResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01a0f0e2-7c1a-7000-8000-000000000001,
  "template_id": 01a0f0e2-7c1a-7000-8000-000000000010,
  "name": Stripe customers,
  "enabled": true,
  "url": https://api.omnismith.io/v1/inbound/01a0f0e2-7c1a-7000-8000-0000000000aa/01a0f0e2-7c1a-7000-8000-000000000001,
  "signature": {"preset":"stripe"},
  "mapping": null,
  "delivery_id_source": null,
  "secrets": null,
  "last_signature_failure_at": null,
  "created_by": demo@omnismith.io,
  "created_at": null,
  "updated_at": null,
} satisfies InboundEndpointResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboundEndpointResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


