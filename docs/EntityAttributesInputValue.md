
# EntityAttributesInputValue


## Properties

Name | Type
------------ | -------------
`value` | number
`updated_at` | Date
`op` | string

## Example

```typescript
import type { EntityAttributesInputValue } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "value": 1,
  "updated_at": 2026-09-12T12:23:52Z,
  "op": null,
} satisfies EntityAttributesInputValue

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityAttributesInputValue
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


