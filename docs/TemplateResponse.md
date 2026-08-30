
# TemplateResponse

Template schema details including attribute bindings, default values, and visual groups.

## Properties

Name | Type
------------ | -------------
`id` | string
`slug` | string
`name` | string
`description` | string
`category` | string
`attribute_ids` | Array&lt;string&gt;
`attributes` | [Array&lt;TemplateResponseAttributesInner&gt;](TemplateResponseAttributesInner.md)
`groups` | [Array&lt;TemplateGroupResponse&gt;](TemplateGroupResponse.md)
`created_at` | Date
`updated_at` | Date
`deleted_at` | Date

## Example

```typescript
import type { TemplateResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "slug": product_sku,
  "name": Product SKU,
  "description": E-commerce physical product catalog schema,
  "category": Catalog,
  "attribute_ids": null,
  "attributes": null,
  "groups": null,
  "created_at": 2026-01-15T10:30Z,
  "updated_at": 2026-01-15T10:30Z,
  "deleted_at": null,
} satisfies TemplateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


