
# BiSchemaField

Connector-friendly field definition for BI datasets

## Properties

Name | Type
------------ | -------------
`template_id` | string
`template_name` | string
`column_name` | string
`label` | string
`source` | string
`attribute_id` | string
`attribute_name` | string
`attribute_type` | string
`data_type` | string
`reference_target_template_id` | string
`reference_target_attribute_id` | string
`list_options` | [Array&lt;BiFieldOption&gt;](BiFieldOption.md)

## Example

```typescript
import type { BiSchemaField } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010001,
  "template_name": Product Catalog,
  "column_name": unit_price,
  "label": Unit Price,
  "source": attribute,
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010002,
  "attribute_name": Unit Price,
  "attribute_type": dimension,
  "data_type": number,
  "reference_target_template_id": 018b2f1b-8c1a-75b3-8000-7f0000010005,
  "reference_target_attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010006,
  "list_options": null,
} satisfies BiSchemaField

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BiSchemaField
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


