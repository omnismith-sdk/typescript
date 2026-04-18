
# CreateProjectRequest


## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`id` | string

## Example

```typescript
import type { CreateProjectRequest } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "name": My Project,
  "description": A description of the project,
  "id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
} satisfies CreateProjectRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateProjectRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


