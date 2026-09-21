
# EntityAttributesInputValueAnyOf

Backfill object: the same value plus the moment it was observed, for importing history.

## Properties

Name | Type
------------ | -------------
`value` | [EntityAttributesInputValueAnyOfValue](EntityAttributesInputValueAnyOfValue.md)
`updated_at` | Date

## Example

```typescript
import type { EntityAttributesInputValueAnyOf } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "value": null,
  "updated_at": 2026-09-12T12:23:52Z,
} satisfies EntityAttributesInputValueAnyOf

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityAttributesInputValueAnyOf
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


