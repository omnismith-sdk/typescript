
# ReferenceConfigResponse

Reference configuration for a Reference-type attribute

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`target_template_id` | string
`target_attribute_id` | string

## Example

```typescript
import type { ReferenceConfigResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": null,
  "target_template_id": null,
  "target_attribute_id": null,
} satisfies ReferenceConfigResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ReferenceConfigResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


