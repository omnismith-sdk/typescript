
# ProjectSchemaResponse

Complete project schema including attributes, templates, list items, and reference configs

## Properties

Name | Type
------------ | -------------
`attributes` | [Array&lt;AttributeResponse&gt;](AttributeResponse.md)
`templates` | [Array&lt;TemplateResponse&gt;](TemplateResponse.md)
`list_items` | [Array&lt;ListItemResponse&gt;](ListItemResponse.md)
`reference_configs` | [Array&lt;ReferenceConfigResponse&gt;](ReferenceConfigResponse.md)

## Example

```typescript
import type { ProjectSchemaResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "attributes": null,
  "templates": null,
  "list_items": null,
  "reference_configs": null,
} satisfies ProjectSchemaResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectSchemaResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


