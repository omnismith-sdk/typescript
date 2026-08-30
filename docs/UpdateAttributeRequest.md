
# UpdateAttributeRequest

Payload for full attribute update.

## Properties

Name | Type
------------ | -------------
`name` | string
`template_ids` | Array&lt;string&gt;
`description` | string
`reference_config` | [PatchAttributeRequestReferenceConfig](PatchAttributeRequestReferenceConfig.md)
`data_type` | number
`slug` | string

## Example

```typescript
import type { UpdateAttributeRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Product Color Variant,
  "template_ids": null,
  "description": Color variant of product SKU,
  "reference_config": null,
  "data_type": 0,
  "slug": product_color_variant,
} satisfies UpdateAttributeRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateAttributeRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


