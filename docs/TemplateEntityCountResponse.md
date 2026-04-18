
# TemplateEntityCountResponse

Entity count for a template

## Properties

Name | Type
------------ | -------------
`template_id` | string
`entity_count` | number

## Example

```typescript
import type { TemplateEntityCountResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": null,
  "entity_count": 42,
} satisfies TemplateEntityCountResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateEntityCountResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


