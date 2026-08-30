
# BiTemplateRowsResponse

Flat row-based dataset for BI tooling

## Properties

Name | Type
------------ | -------------
`columns` | [Array&lt;BiSchemaField&gt;](BiSchemaField.md)
`data` | Array&lt;object&gt;
`total` | number
`limit` | number
`offset` | number

## Example

```typescript
import type { BiTemplateRowsResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "columns": null,
  "data": null,
  "total": 150,
  "limit": 50,
  "offset": 0,
} satisfies BiTemplateRowsResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BiTemplateRowsResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


