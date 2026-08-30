
# BiFieldOption

Allowed option for list-type BI fields

## Properties

Name | Type
------------ | -------------
`id` | string
`value` | string
`sort_order` | number

## Example

```typescript
import type { BiFieldOption } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010020,
  "value": In Stock,
  "sort_order": 1,
} satisfies BiFieldOption

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BiFieldOption
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


