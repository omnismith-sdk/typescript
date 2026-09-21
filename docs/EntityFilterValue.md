
# EntityFilterValue

A string for eq / neq / gt / lt / like / not-like; a non-empty list of strings for in / not-in; exactly `[lower, upper]` (inclusive) for between; omitted for empty / not-empty. List and reference attributes compare the stored id, never the label.

## Properties

Name | Type
------------ | -------------

## Example

```typescript
import type { EntityFilterValue } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
} satisfies EntityFilterValue

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityFilterValue
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


