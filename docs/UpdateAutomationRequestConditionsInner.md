
# UpdateAutomationRequestConditionsInner


## Properties

Name | Type
------------ | -------------
`attributeId` | string
`operator` | string
`value` | any
`mode` | string

## Example

```typescript
import type { UpdateAutomationRequestConditionsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "attributeId": 01912ecb-4654-7890-a1b2-c3d4e5f60077,
  "operator": eq,
  "value": closed_won,
  "mode": current,
} satisfies UpdateAutomationRequestConditionsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateAutomationRequestConditionsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


