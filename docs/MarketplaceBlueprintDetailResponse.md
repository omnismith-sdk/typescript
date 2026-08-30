
# MarketplaceBlueprintDetailResponse

Full blueprint detail representation including packaged schema definitions and demo data

## Properties

Name | Type
------------ | -------------
`id` | string
`user_id` | string
`title` | string
`description` | string
`metadata` | [MarketplaceBlueprintDetailResponseMetadata](MarketplaceBlueprintDetailResponseMetadata.md)
`blueprint` | object
`is_featured` | boolean
`created_at` | Date
`updated_at` | Date

## Example

```typescript
import type { MarketplaceBlueprintDetailResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01912ecb-4654-7890-a1b2-c3d4e5f60003,
  "user_id": 01912ecb-4654-7890-a1b2-c3d4e5f60000,
  "title": CRM Pipeline & Lead Tracker,
  "description": A complete CRM pipeline template with contacts, deals, and activities.,
  "metadata": null,
  "blueprint": null,
  "is_featured": false,
  "created_at": 2026-08-26T12:00Z,
  "updated_at": 2026-08-26T12:00Z,
} satisfies MarketplaceBlueprintDetailResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketplaceBlueprintDetailResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


