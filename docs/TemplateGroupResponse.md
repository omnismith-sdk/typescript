
# TemplateGroupResponse

Visual attribute group details for organizing template fields into UI sections.

## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`icon` | string
`columns` | number
`attribute_ids` | Array&lt;string&gt;

## Example

```typescript
import type { TemplateGroupResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010020,
  "name": General Information,
  "description": Primary identifying fields,
  "icon": info,
  "columns": 2,
  "attribute_ids": null,
} satisfies TemplateGroupResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TemplateGroupResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


