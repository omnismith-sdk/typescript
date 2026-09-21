
# EntityAttributeValue

Verbose attribute value item returned when `verbose=true`: raw serialized value, resolved display label for references and list items, and the attribute identity

## Properties

Name | Type
------------ | -------------
`id` | string
`slug` | string
`value` | string
`custom_value` | string
`reference_entity_id` | string

## Example

```typescript
import type { EntityAttributeValue } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010002,
  "slug": price,
  "value": 129.99,
  "custom_value": Electronics > Audio,
  "reference_entity_id": 018b2f1b-8c1a-75b3-8000-7f0000010005,
} satisfies EntityAttributeValue

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityAttributeValue
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


