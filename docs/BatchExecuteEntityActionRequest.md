
# BatchExecuteEntityActionRequest

The records to run the action on and the values for its fields, shared by every record.

## Properties

Name | Type
------------ | -------------
`entity_ids` | Array&lt;string&gt;
`values` | [{ [key: string]: EntityAttributesInputValue; }](EntityAttributesInputValue.md)
`atomic` | boolean

## Example

```typescript
import type { BatchExecuteEntityActionRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "entity_ids": ["018b2f1b-8c1a-75b3-8000-7f0000010000","018b2f1b-8c1a-75b3-8000-7f0000010001"],
  "values": null,
  "atomic": false,
} satisfies BatchExecuteEntityActionRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as BatchExecuteEntityActionRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


