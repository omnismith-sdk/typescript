
# CreateAttributeRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`attribute_type` | number
`data_type` | number
`template_ids` | Array&lt;string&gt;
`description` | string
`reference_config` | [CreateAttributeRequestReferenceConfig](CreateAttributeRequestReferenceConfig.md)
`id` | string

## Example

```typescript
import type { CreateAttributeRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Color,
  "attribute_type": 0,
  "data_type": 0,
  "template_ids": null,
  "description": Product color,
  "reference_config": null,
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
} satisfies CreateAttributeRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAttributeRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


