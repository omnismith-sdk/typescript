
# ResolvedStatBlockResponse

Computed result for a stat KPI counter block

## Properties

Name | Type
------------ | -------------
`block_id` | string
`title` | string
`type` | string
`count` | number

## Example

```typescript
import type { ResolvedStatBlockResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "block_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  "title": Active Gateways Count,
  "type": stat,
  "count": 42,
} satisfies ResolvedStatBlockResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResolvedStatBlockResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


