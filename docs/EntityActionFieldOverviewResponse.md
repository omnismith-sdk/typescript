
# EntityActionFieldOverviewResponse

Field required or prompted from the operator when executing this action.

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`attribute_slug` | string
`required` | boolean
`hint` | string

## Example

```typescript
import type { EntityActionFieldOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "attribute_slug": resolution_notes,
  "required": true,
  "hint": Reason for closing ticket,
} satisfies EntityActionFieldOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionFieldOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


