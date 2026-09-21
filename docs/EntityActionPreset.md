
# EntityActionPreset

One value the action writes silently when it runs. Presets win over submitted values.

## Properties

Name | Type
------------ | -------------
`attribute_id` | string
`value` | string

## Example

```typescript
import type { EntityActionPreset } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "value": 018b2f1b-8c1a-75b3-8000-7f0000010020,
} satisfies EntityActionPreset

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionPreset
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


