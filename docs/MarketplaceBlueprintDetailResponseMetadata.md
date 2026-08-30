
# MarketplaceBlueprintDetailResponseMetadata

Blueprint metadata including keywords and install stats

## Properties

Name | Type
------------ | -------------
`keywords` | Array&lt;string&gt;
`installs` | number
`version` | number

## Example

```typescript
import type { MarketplaceBlueprintDetailResponseMetadata } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "keywords": ["crm","sales","leads"],
  "installs": 142,
  "version": 1,
} satisfies MarketplaceBlueprintDetailResponseMetadata

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as MarketplaceBlueprintDetailResponseMetadata
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


