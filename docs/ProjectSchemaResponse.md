
# ProjectSchemaResponse

Consolidated schema graph containing templates, attributes, choice options, references, business rules, and actions in a concise, token-efficient shape.

## Properties

Name | Type
------------ | -------------
`project_id` | string
`project_name` | string
`templates` | [Array&lt;TemplateOverviewResponse&gt;](TemplateOverviewResponse.md)
`attributes` | [Array&lt;AttributeOverviewResponse&gt;](AttributeOverviewResponse.md)

## Example

```typescript
import type { ProjectSchemaResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "project_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "project_name": Omnismith Production,
  "templates": null,
  "attributes": null,
} satisfies ProjectSchemaResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ProjectSchemaResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


