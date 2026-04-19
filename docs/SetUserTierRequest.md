
# SetUserTierRequest


## Properties

Name | Type
------------ | -------------
`tier_id` | string
`reason` | string

## Example

```typescript
import type { SetUserTierRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "tier_id": 00000000-0000-0000-0000-000000000002,
  "reason": manual,
} satisfies SetUserTierRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SetUserTierRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


