
# AutomationResponseTrigger

Event trigger configuration defining when this automation fires

## Properties

Name | Type
------------ | -------------
`type` | string
`templateId` | string
`attributeId` | string
`actionId` | string

## Example

```typescript
import type { AutomationResponseTrigger } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "type": on_attribute_changed,
  "templateId": 01912ecb-4654-7890-a1b2-c3d4e5f60088,
  "attributeId": 01912ecb-4654-7890-a1b2-c3d4e5f60077,
  "actionId": 01a09900-0000-7000-8000-000000000001,
} satisfies AutomationResponseTrigger

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationResponseTrigger
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


