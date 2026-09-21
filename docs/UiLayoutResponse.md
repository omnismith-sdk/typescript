
# UiLayoutResponse

Consolidated visual form layout configurations, icons, and display rankings for the active project.

## Properties

Name | Type
------------ | -------------
`project_id` | string
`project_name` | string
`templates` | [Array&lt;TemplateLayoutResponse&gt;](TemplateLayoutResponse.md)
`actions` | [Array&lt;ActionLayoutResponse&gt;](ActionLayoutResponse.md)
`list_items` | [Array&lt;ListItemLayoutResponse&gt;](ListItemLayoutResponse.md)

## Example

```typescript
import type { UiLayoutResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "project_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "project_name": Omnismith Production,
  "templates": null,
  "actions": null,
  "list_items": null,
} satisfies UiLayoutResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UiLayoutResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


