
# ResolvedChartBlockResponse

Computed result for a time-series telemetry chart block aggregated across query intervals

## Properties

Name | Type
------------ | -------------
`block_id` | string
`title` | string
`type` | string
`bucket_width` | string
`series` | [Array&lt;ResolvedChartBlockResponseSeriesInner&gt;](ResolvedChartBlockResponseSeriesInner.md)

## Example

```typescript
import type { ResolvedChartBlockResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "block_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  "title": Gateway Temperature History,
  "type": chart,
  "bucket_width": 1 hour,
  "series": null,
} satisfies ResolvedChartBlockResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResolvedChartBlockResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


