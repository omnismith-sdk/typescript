
# AttributeOverviewResponse

Schema attribute definition with semantic type, embedded list options, and reference linking.

## Properties

Name | Type
------------ | -------------
`id` | string
`slug` | string
`name` | string
`type` | string
`description` | string
`options` | [Array&lt;ListOptionOverviewResponse&gt;](ListOptionOverviewResponse.md)
`reference` | [ReferenceOverviewResponse](ReferenceOverviewResponse.md)

## Example

```typescript
import type { AttributeOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "slug": component,
  "name": Component,
  "type": list,
  "description": Which part of the system this touches,
  "options": null,
  "reference": null,
} satisfies AttributeOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AttributeOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


