
# CheckoutResponse

Checkout session details

## Properties

Name | Type
------------ | -------------
`checkout_url` | string
`checkout_id` | string

## Example

```typescript
import type { CheckoutResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "checkout_url": null,
  "checkout_id": null,
} satisfies CheckoutResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CheckoutResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


