
# UpdateTemplateRequest

Payload for full template update.

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
`slug` | string

## Example

```typescript
import type { UpdateTemplateRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attributes": null,
  "groups": null,
  "name": Product SKU,
  "description": Updated e-commerce product schema,
  "category": Catalog,
  "attribute_ids": null,
  "attribute_slugs": null,
  "slug": product_sku,
} satisfies UpdateTemplateRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateTemplateRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


