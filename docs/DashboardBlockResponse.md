
# DashboardBlockResponse

Dashboard visualization block details including type, title, grid placement, and query configurations

## Properties

Name | Type
------------ | -------------
`id` | string
`dashboard_id` | string
`type` | string
`title` | string
`config` | object
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { DashboardBlockResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  "dashboard_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  "type": chart,
  "title": Gateway Temperature History,
  "config": {"template_id":"0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b","metric_attribute_id":"0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6d","aggregate":"avg","bucket_width":"1 hour","time_window":86400,"x":0,"y":0,"cols":6,"rows":4},
  "created_at": 2026-08-26T12:00Z,
  "updated_at": 2026-08-26T12:30Z,
} satisfies DashboardBlockResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as DashboardBlockResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


