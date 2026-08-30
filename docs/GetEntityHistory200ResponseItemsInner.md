
# GetEntityHistory200ResponseItemsInner


## Properties

Name | Type
------------ | -------------
`created_at` | Date
`attribute_id` | string
`old_value` | string
`value` | string
`entity_id` | string
`author_email` | string

## Example

```typescript
import type { GetEntityHistory200ResponseItemsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "created_at": 2026-08-26T12:05Z,
  "attribute_id": 018b2f1b-8c1a-75b3-8000-7f0000010002,
  "old_value": 129.99,
  "value": 149.99,
  "entity_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "author_email": demo@omnismith.io,
} satisfies GetEntityHistory200ResponseItemsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as GetEntityHistory200ResponseItemsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


