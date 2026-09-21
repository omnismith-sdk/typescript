
# ActionLayoutResponse

Visual UI presentation details for an entity action.

## Properties

Name | Type
------------ | -------------
`action_id` | string
`template_id` | string
`icon` | string
`sort_order` | number

## Example

```typescript
import type { ActionLayoutResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "action_id": 01a09900-0000-7000-8000-000000000001,
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "icon": check_circle,
  "sort_order": 0,
} satisfies ActionLayoutResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ActionLayoutResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


