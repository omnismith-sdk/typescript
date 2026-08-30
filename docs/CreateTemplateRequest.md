
# CreateTemplateRequest

Payload for creating a new dynamic schema template (content type).

## Properties

Name | Type
------------ | -------------
`attributes` | [Array&lt;TemplateAttributeInput&gt;](TemplateAttributeInput.md)
`groups` | [Array&lt;TemplateGroupInput&gt;](TemplateGroupInput.md)
`name` | string
`description` | string
`category` | string
`attribute_ids` | Array&lt;string&gt;
`attribute_slugs` | Array&lt;string&gt;
`id` | string
`slug` | string

## Example

```typescript
import type { CreateTemplateRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attributes": null,
  "groups": null,
  "name": Product SKU,
  "description": E-commerce physical product catalog schema,
  "category": Catalog,
  "attribute_ids": null,
  "attribute_slugs": null,
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "slug": product_sku,
} satisfies CreateTemplateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateTemplateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


