
# UpdateDashboardRequestConfig

Updated dashboard canvas (minCols: 12, maxCols: 12) and auto-refresh configuration

## Properties

Name | Type
------------ | -------------
`minCols` | number
`maxCols` | number
`minRows` | number
`maxRows` | number
`auto_refresh` | number
`thumbnail` | string

## Example

```typescript
import type { UpdateDashboardRequestConfig } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "minCols": 12,
  "maxCols": 12,
  "minRows": 1,
  "maxRows": 100,
  "auto_refresh": 0,
  "thumbnail": null,
} satisfies UpdateDashboardRequestConfig

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateDashboardRequestConfig
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


