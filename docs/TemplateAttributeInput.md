
# TemplateAttributeInput

Specification for associating an attribute with a template, including optional per-template default value. Specify either attribute_id or attribute_slug.

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`attribute_slug` | string
`default_value` | string

## Example

```typescript
import type { TemplateAttributeInput } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "attribute_slug": product_color,
  "default_value": 019a6b2c-8c3a-7c2e-8b3f-6c8a1a2b3c4d,
} satisfies TemplateAttributeInput

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateAttributeInput
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


