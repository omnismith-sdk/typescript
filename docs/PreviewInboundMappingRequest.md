
# PreviewInboundMappingRequest

Send exactly one of `body` and `delivery_id`.

## Properties

Name | Type
------------ | -------------
`body` | { [key: string]: any; }
`delivery_id` | string
`mapping` | { [key: string]: any; }

## Example

```typescript
import type { PreviewInboundMappingRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "body": {"id":"evt_1","type":"customer.created","data":{"object":{"id":"cus_1","email":"demo@omnismith.io"}}},
  "delivery_id": null,
  "mapping": null,
} satisfies PreviewInboundMappingRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PreviewInboundMappingRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


