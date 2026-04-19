
# TierResponseLimits


## Properties

Name | Type
------------ | -------------
`attributes` | number
`templates` | number
`entities` | number
`disk_space_gb` | number
`projects` | number
`dashboards` | number
`automations` | number
`channels` | number
`metric_ingestions_per_month` | number
`dimension_updates_per_month` | number
`ai_credits` | number

## Example

```typescript
import type { TierResponseLimits } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attributes": 100,
  "templates": 25,
  "entities": 5000,
  "disk_space_gb": 10,
  "projects": 5,
  "dashboards": 2,
  "automations": 10,
  "channels": 5,
  "metric_ingestions_per_month": 1000000,
  "dimension_updates_per_month": 5000,
  "ai_credits": 500,
} satisfies TierResponseLimits

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TierResponseLimits
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


