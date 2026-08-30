
# EntityResponse

Hydrated dynamic entity record conforming to a template schema, including all dimension and metric attribute values

## Properties

Name | Type
------------ | -------------
`id` | string
`template_id` | string
`template_slug` | string
`created_at` | Date
`updated_at` | Date
`attribute_values` | [{ [key: string]: EntityAttributeValue; }](EntityAttributeValue.md)

## Example

```typescript
import type { EntityResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010001,
  "template_slug": product_catalog,
  "created_at": 2026-08-26T12:00Z,
  "updated_at": 2026-08-26T12:05Z,
  "attribute_values": null,
} satisfies EntityResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


