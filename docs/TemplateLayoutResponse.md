
# TemplateLayoutResponse

Visual layout configuration for organizing template fields into UI sections.

## Properties

Name | Type
------------ | -------------
`template_id` | string
`category` | string
`groups` | [Array&lt;TemplateGroupResponse&gt;](TemplateGroupResponse.md)

## Example

```typescript
import type { TemplateLayoutResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "category": Engineering,
  "groups": null,
} satisfies TemplateLayoutResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateLayoutResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


