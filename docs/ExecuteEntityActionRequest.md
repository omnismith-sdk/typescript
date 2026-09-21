
# ExecuteEntityActionRequest

The values for the action\'s fields. Omit `values` (or send `{}`) for an action without fields.

## Properties

Name | Type
------------ | -------------
`values` | [{ [key: string]: EntityAttributesInputValue; }](EntityAttributesInputValue.md)

## Example

```typescript
import type { ExecuteEntityActionRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "values": null,
} satisfies ExecuteEntityActionRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExecuteEntityActionRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


