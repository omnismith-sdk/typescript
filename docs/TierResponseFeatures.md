
# TierResponseFeatures


## Properties

Name | Type
------------ | -------------
`api_access` | boolean
`export_to_csv` | boolean
`sso_enabled` | boolean
`audit_logs` | boolean
`history_retention_days` | number

## Example

```typescript
import type { TierResponseFeatures } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "api_access": null,
  "export_to_csv": null,
  "sso_enabled": null,
  "audit_logs": null,
  "history_retention_days": null,
} satisfies TierResponseFeatures

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TierResponseFeatures
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


