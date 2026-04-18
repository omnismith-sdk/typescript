
# ResolvedChartBlockResponseSeriesInner


## Properties

Name | Type
------------ | -------------
`entity_id` | string
`entity_name` | string
`data_points` | [Array&lt;GetEntityChart200ResponseSeriesInnerDataInner&gt;](GetEntityChart200ResponseSeriesInnerDataInner.md)

## Example

```typescript
import type { ResolvedChartBlockResponseSeriesInner } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "entity_id": null,
  "entity_name": null,
  "data_points": null,
} satisfies ResolvedChartBlockResponseSeriesInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResolvedChartBlockResponseSeriesInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


