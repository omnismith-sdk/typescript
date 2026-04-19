
# CreateEntityRequest


## Properties

Name | Type
------------ | -------------
`template_id` | string
`attribute_values` | [Array&lt;CreateEntityRequestAttributeValuesInner&gt;](CreateEntityRequestAttributeValuesInner.md)
`id` | string

## Example

```typescript
import type { CreateEntityRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": null,
  "attribute_values": null,
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
} satisfies CreateEntityRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateEntityRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


