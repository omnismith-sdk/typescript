
# BiTimeSeriesRow

Flat time-series row for BI tooling

## Properties

Name | Type
------------ | -------------
`template_id` | string
`entity_id` | string
`attribute_id` | string
`attribute_name` | string
`bucket_time` | Date
`value` | number

## Example

```typescript
import type { BiTimeSeriesRow } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010001,
  "entity_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "attribute_name": CPU Utilization,
  "bucket_time": 2026-08-26T12:00Z,
  "value": 24.5,
} satisfies BiTimeSeriesRow

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BiTimeSeriesRow
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


