
# CreateDashboardBlockRequest

Payload for adding a visualization widget to a dashboard canvas. Requires a block type (stat, chart, gauge, list), header title, and type-specific configuration including 12-column grid layout (x, y, cols, rows) and metric query parameters.

## Properties

Name | Type
------------ | -------------
`type` | string
`title` | string
`config` | [CreateDashboardBlockRequestConfig](CreateDashboardBlockRequestConfig.md)

## Example

```typescript
import type { CreateDashboardBlockRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "type": chart,
  "title": CPU Utilization — Time Series,
  "config": null,
} satisfies CreateDashboardBlockRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateDashboardBlockRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


