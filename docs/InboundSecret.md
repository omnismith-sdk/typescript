
# InboundSecret

A secret deliveries are verified with. Only a hint is shown.

## Properties

Name | Type
------------ | -------------
`id` | string
`hint` | string
`created_at` | Date

## Example

```typescript
import type { InboundSecret } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "hint": x9Qa,
  "created_at": null,
} satisfies InboundSecret

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboundSecret
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


