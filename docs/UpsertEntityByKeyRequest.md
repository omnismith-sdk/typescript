
# UpsertEntityByKeyRequest

The external key that identifies the record, and the attribute values to write to it

## Properties

Name | Type
------------ | -------------
`external_key` | string
`attributes` | [{ [key: string]: EntityAttributesInputValue; }](EntityAttributesInputValue.md)

## Example

```typescript
import type { UpsertEntityByKeyRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "external_key": stripe:cus_NffrFeUfNV2Hib,
  "attributes": null,
} satisfies UpsertEntityByKeyRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpsertEntityByKeyRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


