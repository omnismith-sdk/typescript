
# CreateWorkspaceRequest

Payload for creating a new workspace workbench

## Properties

Name | Type
------------ | -------------
`name` | string
`description` | string
`layout` | string
`is_default` | boolean
`initial_template_ids` | Array&lt;string&gt;

## Example

```typescript
import type { CreateWorkspaceRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Operations Hub,
  "description": Daily fleet monitoring and telemetry operations workbench,
  "layout": split-v,
  "is_default": false,
  "initial_template_ids": ["0190a1b2-c3d4-7e8f-9a0b-1c2d3e4f5a6b"],
} satisfies CreateWorkspaceRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateWorkspaceRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


