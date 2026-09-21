
# ReferenceOverviewResponse

Foreign entity reference target configuration for reference-type attributes.

## Properties

Name | Type
------------ | -------------
`target_template_id` | string
`target_template_slug` | string
`target_attribute_id` | string
`target_attribute_slug` | string

## Example

```typescript
import type { ReferenceOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "target_template_id": 018b2f1b-8c1a-75b3-8000-7f0000010002,
  "target_template_slug": company,
  "target_attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010003,
  "target_attribute_slug": company_name,
} satisfies ReferenceOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ReferenceOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


