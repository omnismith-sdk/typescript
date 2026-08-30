
# CreateDashboardRequest

Payload for creating a new analytics and telemetry dashboard canvas. Omnismith dashboards utilize a 12-column grid layout.

## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`config` | [CreateDashboardRequestConfig](CreateDashboardRequestConfig.md)

## Example

```typescript
import type { CreateDashboardRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Infrastructure & Operations Hub,
  "description": Live overview of cloud server fleet health and CPU telemetry.,
  "config": null,
} satisfies CreateDashboardRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateDashboardRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


