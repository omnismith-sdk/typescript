
# UpdateEntityRequest


## Properties

Name | Type
------------ | -------------
`attribute_values` | [Array&lt;CreateEntityRequestAttributeValuesInner&gt;](CreateEntityRequestAttributeValuesInner.md)

## Example

```typescript
import type { UpdateEntityRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_values": null,
} satisfies UpdateEntityRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateEntityRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


