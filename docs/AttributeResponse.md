
# AttributeResponse

Complete schema attribute metadata and configuration.

## Properties

Name | Type
------------ | -------------
`id` | string
`slug` | string
`name` | string
`description` | string
`attribute_type` | number
`data_type` | number
`template_ids` | Array&lt;string&gt;
`reference_config` | [AttributeResponseReferenceConfig](AttributeResponseReferenceConfig.md)
`created_at` | Date
`updated_at` | Date
`deleted_at` | Date

## Example

```typescript
import type { AttributeResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "slug": product_color,
  "name": Product Color,
  "description": Product color specification,
  "attribute_type": 0,
  "data_type": 0,
  "template_ids": null,
  "reference_config": null,
  "created_at": 2026-01-15T10:30Z,
  "updated_at": 2026-01-15T10:30Z,
  "deleted_at": null,
} satisfies AttributeResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AttributeResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


