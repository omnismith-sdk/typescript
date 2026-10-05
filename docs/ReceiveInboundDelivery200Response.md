
# ReceiveInboundDelivery200Response


## Properties

Name | Type
------------ | -------------
`status` | string
`log_id` | string
`entity_ids` | Array&lt;string&gt;
`reason` | string
`items` | Array&lt;{ [key: string]: any; }&gt;
`errors` | { [key: string]: any; }

## Example

```typescript
import type { ReceiveInboundDelivery200Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "status": null,
  "log_id": null,
  "entity_ids": null,
  "reason": duplicate,
  "items": null,
  "errors": null,
} satisfies ReceiveInboundDelivery200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ReceiveInboundDelivery200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


