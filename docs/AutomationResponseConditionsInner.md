
# AutomationResponseConditionsInner


## Properties

Name | Type
------------ | -------------
`attributeId` | string
`operator` | string
`value` | any
`mode` | string

## Example

```typescript
import type { AutomationResponseConditionsInner } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "attributeId": null,
  "operator": eq,
  "value": null,
  "mode": current,
} satisfies AutomationResponseConditionsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AutomationResponseConditionsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


