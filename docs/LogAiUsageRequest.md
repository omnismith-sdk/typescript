
# LogAiUsageRequest


## Properties

Name | Type
------------ | -------------
`credits_deducted` | number
`model` | string
`input_tokens` | number
`output_tokens` | number

## Example

```typescript
import type { LogAiUsageRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "credits_deducted": 10,
  "model": gpt-4,
  "input_tokens": 100,
  "output_tokens": 50,
} satisfies LogAiUsageRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as LogAiUsageRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


