
# ExecuteEntityActionResponse

Receipt of an executed action: the record, the action, and exactly what was written (submitted values with presets applied). The record itself is not returned because its read model is projected asynchronously; fetch it with `GET /entities/{id}` once the change is needed.

## Properties

Name | Type
------------ | -------------
`entity_id` | string
`template_id` | string
`action` | [ExecuteEntityActionResponseAction](ExecuteEntityActionResponseAction.md)
`attributes` | { [key: string]: string; }

## Example

```typescript
import type { ExecuteEntityActionResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "entity_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "template_id": 018b2f1b-8c1a-75b3-8000-7f0000010010,
  "action": null,
  "attributes": {"status":"018b2f1b-8c1a-75b3-8000-7f0000010020","attendee_count":"4"},
} satisfies ExecuteEntityActionResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExecuteEntityActionResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


