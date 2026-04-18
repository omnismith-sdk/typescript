
# TierResponse

Subscription tier details

## Properties

Name | Type
------------ | -------------
`id` | string
`title` | string
`description` | string
`price_cents` | number
`currency` | string
`limits` | [TierResponseLimits](TierResponseLimits.md)
`features` | [TierResponseFeatures](TierResponseFeatures.md)

## Example

```typescript
import type { TierResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "title": Pro,
  "description": null,
  "price_cents": 2900,
  "currency": USD,
  "limits": null,
  "features": null,
} satisfies TierResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as TierResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


