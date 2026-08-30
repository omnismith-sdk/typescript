
# CreateDashboardBlockRequestConfig

Widget configuration object containing data source, metrics, time windows, and 12-column grid layout properties.

## Properties

Name | Type
------------ | -------------
`template_id` | string
`metric_attribute_id` | string
`time_window` | number
`bucket_width` | string
`aggregate` | string
`entity_limit` | number
`min` | number
`max` | number
`unit` | string
`start_color` | string
`mid_color` | string
`end_color` | string
`limit` | number
`sort` | object
`visible_attributes` | Array&lt;string&gt;
`filters` | [Array&lt;CreateDashboardBlockRequestConfigFiltersInner&gt;](CreateDashboardBlockRequestConfigFiltersInner.md)
`x` | number
`y` | number
`cols` | number
`rows` | number

## Example

```typescript
import type { CreateDashboardBlockRequestConfig } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  "metric_attribute_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6d,
  "time_window": 86400,
  "bucket_width": 1 hour,
  "aggregate": avg,
  "entity_limit": 10,
  "min": 0,
  "max": 100,
  "unit": %,
  "start_color": #3b82f6,
  "mid_color": #f59e0b,
  "end_color": #06b6d4,
  "limit": 10,
  "sort": {"created_at":"desc"},
  "visible_attributes": ["created_at","0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6d"],
  "filters": null,
  "x": 0,
  "y": 0,
  "cols": 6,
  "rows": 3,
} satisfies CreateDashboardBlockRequestConfig

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateDashboardBlockRequestConfig
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


