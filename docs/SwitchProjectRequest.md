
# SwitchProjectRequest

Payload for switching the active project context

## Properties

Name | Type
------------ | -------------
`project_id` | string

## Example

```typescript
import type { SwitchProjectRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "project_id": 018b2f1b-7c3a-7d2e-8f1a-2b3c4d5e6f7a,
} satisfies SwitchProjectRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SwitchProjectRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


