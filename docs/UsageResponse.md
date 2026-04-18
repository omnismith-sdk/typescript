
# UsageResponse

User resource usage statistics

## Properties

Name | Type
------------ | -------------
`attribute_count` | number
`template_count` | number
`entity_count` | number
`project_count` | number
`dashboard_count` | number
`disk_usage_bytes` | number
`monthly_metric_ingestions` | number
`monthly_dimension_updates` | number
`ai_credits_used` | number
`updated_at` | Date

## Example

```typescript
import type { UsageResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_count": 42,
  "template_count": 5,
  "entity_count": 1523,
  "project_count": 3,
  "dashboard_count": 2,
  "disk_usage_bytes": 52428800,
  "monthly_metric_ingestions": 15000,
  "monthly_dimension_updates": 100,
  "ai_credits_used": 125,
  "updated_at": null,
} satisfies UsageResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UsageResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


