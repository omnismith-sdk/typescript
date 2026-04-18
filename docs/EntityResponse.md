
# EntityResponse


## Properties

Name | Type
------------ | -------------
`id` | string
`template_id` | string
`created_at` | string
`updated_at` | string
`attribute_values` | [{ [key: string]: EntityAttributeValue; }](EntityAttributeValue.md)

## Example

```typescript
import type { EntityResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "template_id": null,
  "created_at": null,
  "updated_at": null,
  "attribute_values": null,
} satisfies EntityResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


