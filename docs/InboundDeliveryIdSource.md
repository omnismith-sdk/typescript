
# InboundDeliveryIdSource

Where the sender puts its own id for a delivery. A delivery whose id was already processed in the last 7 days is acknowledged with 200 and not processed again. Without a source, a retried delivery is processed again: record values stay correct, but metric points can be appended twice.

## Properties

Name | Type
------------ | -------------
`from` | string
`path` | string

## Example

```typescript
import type { InboundDeliveryIdSource } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "from": header,
  "path": X-GitHub-Delivery,
} satisfies InboundDeliveryIdSource

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboundDeliveryIdSource
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


