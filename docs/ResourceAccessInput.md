
# ResourceAccessInput


## Properties

Name | Type
------------ | -------------
`resource_type` | string
`resource_id` | string
`access_level` | string

## Example

```typescript
import type { ResourceAccessInput } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "resource_type": null,
  "resource_id": null,
  "access_level": null,
} satisfies ResourceAccessInput

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ResourceAccessInput
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


