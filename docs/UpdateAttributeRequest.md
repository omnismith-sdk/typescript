
# UpdateAttributeRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`template_ids` | Array&lt;string&gt;
`reference_config` | [UpdateAttributeRequestReferenceConfig](UpdateAttributeRequestReferenceConfig.md)

## Example

```typescript
import type { UpdateAttributeRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Color,
  "template_ids": null,
  "reference_config": null,
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


