
# BiTemplateInfo

Template metadata exposed for BI schema discovery

## Properties

Name | Type
------------ | -------------
`template_id` | string
`template_name` | string
`description` | string
`category` | string

## Example

```typescript
import type { BiTemplateInfo } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010001,
  "template_name": Product Catalog,
  "description": Product catalog with dimensions and metrics,
  "category": E-commerce,
} satisfies BiTemplateInfo

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BiTemplateInfo
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


