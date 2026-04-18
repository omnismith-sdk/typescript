
# UsageInsightsResponseUsage


## Properties

Name | Type
------------ | -------------
`attributes` | number
`templates` | number
`entities` | number
`projects` | number
`dashboards` | number
`automations` | number
`channels` | number
`metric_ingestions` | number
`dimension_updates` | number
`ai_credits` | number
`disk_space_mb` | number

## Example

```typescript
import type { UsageInsightsResponseUsage } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "attributes": null,
  "templates": null,
  "entities": null,
  "projects": null,
  "dashboards": null,
  "automations": null,
  "channels": null,
  "metric_ingestions": null,
  "dimension_updates": null,
  "ai_credits": null,
  "disk_space_mb": null,
} satisfies UsageInsightsResponseUsage

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UsageInsightsResponseUsage
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


