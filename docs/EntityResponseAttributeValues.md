
# EntityResponseAttributeValues

Attribute values of the entity. The shape depends on the `verbose` flag of the request: - default (compact): an object mapping attribute slug to the display value, e.g. `{\"price\": \"129.99\", \"status\": \"Open\", \"owner\": \"Platform team\"}`. List, reference and file attributes show their resolved label (list option label, referenced entity display value, original filename); the stored ids behind those labels are in `list_item_ids`, `reference_entity_ids` and `file_ids`. Attributes without a slug are keyed by their UUID. Attributes whose value is empty are omitted. - `verbose=true`: an array of `EntityAttributeValue` items, one per attribute (empty values included), each carrying the attribute `id`, `slug`, raw `value`, resolved `custom_value` and `reference_entity_id`.

## Properties

Name | Type
------------ | -------------

## Example

```typescript
import type { EntityResponseAttributeValues } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
} satisfies EntityResponseAttributeValues

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityResponseAttributeValues
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


