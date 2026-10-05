
# InboundEndpointOverviewResponse

A public URL through which an outside system writes records into the template. Read the full definition and the delivery log with the inbound endpoint tools.

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`enabled` | boolean
`mode` | string
`preset` | string
`url` | string

## Example

```typescript
import type { InboundEndpointOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01a0f0e2-7c1a-7000-8000-000000000001,
  "name": Stripe customers,
  "enabled": true,
  "mode": upsert,
  "preset": stripe,
  "url": https://api.omnismith.io/v1/inbound/01a0f0e2-7c1a-7000-8000-0000000000aa/01a0f0e2-7c1a-7000-8000-000000000001,
} satisfies InboundEndpointOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboundEndpointOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


