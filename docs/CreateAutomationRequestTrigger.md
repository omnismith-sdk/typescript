
# CreateAutomationRequestTrigger

Event trigger defining the lifecycle condition that fires this automation

## Properties

Name | Type
------------ | -------------
`type` | string
`templateId` | string
`attributeId` | string

## Example

```typescript
import type { CreateAutomationRequestTrigger } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "type": on_attribute_changed,
  "templateId": 01912ecb-4654-7890-a1b2-c3d4e5f60088,
  "attributeId": 01912ecb-4654-7890-a1b2-c3d4e5f60077,
} satisfies CreateAutomationRequestTrigger

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateAutomationRequestTrigger
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


