
# SetReferenceConfigRequest

Payload specifying target template and display attribute for a reference relationship.

## Properties

Name | Type
------------ | -------------
`target_template_id` | string
`target_attribute_id` | string

## Example

```typescript
import type { SetReferenceConfigRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "target_template_id": 018b2f1b-8c1a-75b3-8000-7f0000010002,
  "target_attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010003,
} satisfies SetReferenceConfigRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SetReferenceConfigRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


