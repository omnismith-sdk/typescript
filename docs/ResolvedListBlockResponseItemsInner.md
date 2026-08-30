
# ResolvedListBlockResponseItemsInner


## Properties

Name | Type
------------ | -------------
`entity_id` | string
`created_at` | Date
`updated_at` | Date
`attributes` | object

## Example

```typescript
import type { ResolvedListBlockResponseItemsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "entity_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b,
  "created_at": 2026-08-26T12:00Z,
  "updated_at": 2026-08-26T12:30Z,
  "attributes": {"name":"Gateway Alpha","status":"active"},
} satisfies ResolvedListBlockResponseItemsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResolvedListBlockResponseItemsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


