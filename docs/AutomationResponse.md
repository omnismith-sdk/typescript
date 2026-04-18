
# AutomationResponse


## Properties

Name | Type
------------ | -------------
`id` | string
`name` | string
`description` | string
`isEnabled` | boolean
`trigger` | [AutomationResponseTrigger](AutomationResponseTrigger.md)
`conditions` | [Array&lt;AutomationResponseConditionsInner&gt;](AutomationResponseConditionsInner.md)
`actions` | [Array&lt;AutomationResponseActionsInner&gt;](AutomationResponseActionsInner.md)
`cooldownSeconds` | number
`lastTriggeredAt` | Date
`createdAt` | Date
`updatedAt` | Date

## Example

```typescript
import type { AutomationResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "name": Notify on status change,
  "description": Sends alert when status attribute changes,
  "isEnabled": true,
  "trigger": null,
  "conditions": null,
  "actions": null,
  "cooldownSeconds": 60,
  "lastTriggeredAt": null,
  "createdAt": null,
  "updatedAt": null,
} satisfies AutomationResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


