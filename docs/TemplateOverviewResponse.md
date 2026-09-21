
# TemplateOverviewResponse

Template schema definition with bound attributes, validation rules, and executable actions.

## Properties

Name | Type
------------ | -------------
`id` | string
`slug` | string
`name` | string
`description` | string
`attributes` | [Array&lt;TemplateAttributeOverviewResponse&gt;](TemplateAttributeOverviewResponse.md)
`rules` | [Array&lt;EntityRuleOverviewResponse&gt;](EntityRuleOverviewResponse.md)
`actions` | [Array&lt;EntityActionOverviewResponse&gt;](EntityActionOverviewResponse.md)

## Example

```typescript
import type { TemplateOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "slug": dev_ticket,
  "name": Dev Ticket,
  "description": Engineering issue or task,
  "attributes": null,
  "rules": null,
  "actions": null,
} satisfies TemplateOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


