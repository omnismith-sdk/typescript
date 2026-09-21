
# EntityActionOutcome

What happened to one record. `receipt` is set when the action executed; otherwise `error` carries the body the single-record endpoint would have returned.

## Properties

Name | Type
------------ | -------------
`entity_id` | string
`status` | string
`receipt` | [ExecuteEntityActionResponse](ExecuteEntityActionResponse.md)
`error` | [ErrorResponse](ErrorResponse.md)

## Example

```typescript
import type { EntityActionOutcome } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "entity_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "status": executed,
  "receipt": null,
  "error": null,
} satisfies EntityActionOutcome

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionOutcome
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


