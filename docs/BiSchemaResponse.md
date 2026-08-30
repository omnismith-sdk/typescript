
# BiSchemaResponse

Flattened metadata catalog for BI tooling

## Properties

Name | Type
------------ | -------------
`templates` | [Array&lt;BiTemplateInfo&gt;](BiTemplateInfo.md)
`fields` | [Array&lt;BiSchemaField&gt;](BiSchemaField.md)

## Example

```typescript
import type { BiSchemaResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "templates": null,
  "fields": null,
} satisfies BiSchemaResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BiSchemaResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


