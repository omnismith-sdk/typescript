
# IngestMetricsRequestMetricValuesInner


## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`attribute_slug` | string
`value` | string
`updated_at` | Date

## Example

```typescript
import type { IngestMetricsRequestMetricValuesInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "attribute_slug": temperature_celsius,
  "value": 24.5,
  "updated_at": 2026-08-26T12:00Z,
} satisfies IngestMetricsRequestMetricValuesInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as IngestMetricsRequestMetricValuesInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


