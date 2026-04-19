
# SendFeedbackRequest

Payload for submitting user feedback

## Properties

Name | Type
------------ | -------------
`title` | string
`category` | string
`message` | string

## Example

```typescript
import type { SendFeedbackRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "title": Dashboard chart is not rendering correctly,
  "category": Bug Report,
  "message": When I open the dashboard page, the chart widget shows a blank area instead of data.,
} satisfies SendFeedbackRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SendFeedbackRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


