
# UpdateDashboardBlockRequest

Payload for updating a dashboard block configuration, query parameters, or 12-column grid placement

## Properties

Name | Type
------------ | -------------
`title` | string
`config` | [UpdateDashboardBlockRequestConfig](UpdateDashboardBlockRequestConfig.md)

## Example

```typescript
import type { UpdateDashboardBlockRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "title": CPU Utilization — Time Series,
  "config": null,
} satisfies UpdateDashboardBlockRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateDashboardBlockRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


