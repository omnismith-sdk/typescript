
# PublishMarketplaceBlueprintRequest


## Properties

Name | Type
------------ | -------------
`title` | string
`description` | string
`keywords` | Array&lt;string&gt;
`template_ids` | Array&lt;string&gt;
`id` | string

## Example

```typescript
import type { PublishMarketplaceBlueprintRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "title": CRM Pipeline & Lead Tracker,
  "description": A complete CRM pipeline template with contacts, deals, and activities.,
  "keywords": ["crm","sales","deals"],
  "template_ids": ["01912ecb-4654-7890-a1b2-c3d4e5f60088","01912ecb-4654-7890-a1b2-c3d4e5f60089"],
  "id": 01912ecb-4654-7890-a1b2-c3d4e5f60003,
} satisfies PublishMarketplaceBlueprintRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PublishMarketplaceBlueprintRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


