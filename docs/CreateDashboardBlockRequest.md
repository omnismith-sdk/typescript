
# CreateDashboardBlockRequest


## Properties

Name | Type
------------ | -------------
`type` | string
`title` | string
`config` | object

## Example

```typescript
import type { CreateDashboardBlockRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "type": null,
  "title": My Block,
  "config": {"template_id": "uuid", "filters": []},
} satisfies CreateDashboardBlockRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateDashboardBlockRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


