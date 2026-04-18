
# TemplateResponse

Template details

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`category` | string
`attribute_ids` | Array&lt;string&gt;
`created_at` | Date
`updated_at` | Date
`deleted_at` | Date

## Example

```typescript
import type { TemplateResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": null,
  "description": null,
  "category": null,
  "attribute_ids": null,
  "created_at": null,
  "updated_at": null,
  "deleted_at": null,
} satisfies TemplateResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


