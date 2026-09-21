
# BatchOperationInput

One write in a batch. Exact field set per op — create: template, id?, attributes · update: id, attributes · replace: id, attributes · delete: id. Any other field is rejected.

## Properties

Name | Type
------------ | -------------
`op` | string
`id` | string
`template` | string
`attributes` | [{ [key: string]: EntityAttributesInputValue; }](EntityAttributesInputValue.md)

## Example

```typescript
import type { BatchOperationInput } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "op": update,
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "template": product_catalog,
  "attributes": null,
} satisfies BatchOperationInput

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchOperationInput
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


