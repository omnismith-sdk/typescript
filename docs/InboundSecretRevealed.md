
# InboundSecretRevealed

A secret as it is issued. `value` is shown this once and never returned again: give it to whoever configures the sender and do not store it anywhere else.

## Properties

Name | Type
------------ | -------------
`id` | string
`hint` | string
`created_at` | Date
`value` | string

## Example

```typescript
import type { InboundSecretRevealed } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "hint": x9Qa,
  "created_at": null,
  "value": omni_in_dummy_secret_value,
} satisfies InboundSecretRevealed

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as InboundSecretRevealed
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


