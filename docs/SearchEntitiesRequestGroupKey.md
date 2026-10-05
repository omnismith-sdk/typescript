
# SearchEntitiesRequestGroupKey

Narrows the result to one group reported by aggregate_entities: pass the `field` and `value` of a group key back unchanged. `value` null selects the records that have no value for the field. Omit the property to search all records. Combines with filter_groups, global_search and sorting; the total then equals the group\'s count. The field must be groupable (list, reference, string, number, boolean, date or datetime) and the value must have the type aggregate_entities reports for it.

## Properties

Name | Type
------------ | -------------
`field` | string
`value` | [SearchEntitiesRequestGroupKeyValue](SearchEntitiesRequestGroupKeyValue.md)

## Example

```typescript
import type { SearchEntitiesRequestGroupKey } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "field": platform,
  "value": null,
} satisfies SearchEntitiesRequestGroupKey

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchEntitiesRequestGroupKey
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


