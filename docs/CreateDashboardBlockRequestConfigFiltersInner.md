
# CreateDashboardBlockRequestConfigFiltersInner


## Properties

Name | Type
------------ | -------------
`field` | string
`operator` | string
`value` | string
`is_active` | boolean

## Example

```typescript
import type { CreateDashboardBlockRequestConfigFiltersInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "field": status,
  "operator": eq,
  "value": active,
  "is_active": true,
} satisfies CreateDashboardBlockRequestConfigFiltersInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateDashboardBlockRequestConfigFiltersInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


