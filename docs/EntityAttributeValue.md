
# EntityAttributeValue

Structured attribute value including display/custom value for references

## Properties

Name | Type
------------ | -------------
`value` | string
`custom_value` | string
`reference_entity_id` | string

## Example

```typescript
import type { EntityAttributeValue } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "value": null,
  "custom_value": null,
  "reference_entity_id": null,
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


