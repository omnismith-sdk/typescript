
# IngestMetricsRequest

Batch payload of time-series metric observations for an entity

## Properties

Name | Type
------------ | -------------
`metric_values` | [Array&lt;IngestMetricsRequestMetricValuesInner&gt;](IngestMetricsRequestMetricValuesInner.md)

## Example

```typescript
import type { IngestMetricsRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "metric_values": null,
} satisfies IngestMetricsRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IngestMetricsRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


