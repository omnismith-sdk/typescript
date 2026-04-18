
# GetEntityHistory200ResponseItemsInner


## Properties

Name | Type
------------ | -------------
`created_at` | Date
`attribute_id` | string
`value` | string
`entity_id` | string
`author_email` | string

## Example

```typescript
import type { GetEntityHistory200ResponseItemsInner } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "created_at": null,
  "attribute_id": null,
  "value": null,
  "entity_id": null,
  "author_email": null,
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


