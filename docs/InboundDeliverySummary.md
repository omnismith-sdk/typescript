
# InboundDeliverySummary

One row of an endpoint\'s delivery log, without the stored body.

## Properties

Name | Type
------------ | -------------
`id` | string
`received_at` | Date
`delivery_id` | string
`outcome` | string
`http_status` | number
`error` | { [key: string]: any; }
`entity_ids` | Array&lt;string&gt;
`body_truncated` | boolean
`duration_ms` | number
`replay_of` | string
`replayed_by` | string

## Example

```typescript
import type { InboundDeliverySummary } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "received_at": null,
  "delivery_id": null,
  "outcome": null,
  "http_status": 200,
  "error": null,
  "entity_ids": null,
  "body_truncated": null,
  "duration_ms": 42,
  "replay_of": null,
  "replayed_by": null,
} satisfies InboundDeliverySummary

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboundDeliverySummary
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


