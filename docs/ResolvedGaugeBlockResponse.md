
# ResolvedGaugeBlockResponse

Computed result for a gauge meter block

## Properties

Name | Type
------------ | -------------
`block_id` | string
`title` | string
`type` | string
`value` | number
`min` | number
`max` | number
`percentage` | number

## Example

```typescript
import type { ResolvedGaugeBlockResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "block_id": 0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6c,
  "title": CPU Load Average,
  "type": gauge,
  "value": 73.5,
  "min": 0,
  "max": 100,
  "percentage": 73.5,
} satisfies ResolvedGaugeBlockResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResolvedGaugeBlockResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


