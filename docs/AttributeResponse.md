
# AttributeResponse

Attribute details

## Properties

Name | Type
------------ | -------------
`id` | string
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
import type { AttributeResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "attribute_type": null,
  "data_type": null,
  "template_ids": null,
  "reference_config": null,
  "created_at": null,
  "updated_at": null,
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


