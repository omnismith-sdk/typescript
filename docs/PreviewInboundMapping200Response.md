
# PreviewInboundMapping200Response


## Properties

Name | Type
------------ | -------------
`mode` | string
`matched` | boolean
`skipped` | string
`items` | [Array&lt;PreviewInboundMapping200ResponseItemsInner&gt;](PreviewInboundMapping200ResponseItemsInner.md)
`errors` | { [key: string]: Array&lt;string&gt;; }

## Example

```typescript
import type { PreviewInboundMapping200Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "mode": null,
  "matched": null,
  "skipped": null,
  "items": null,
  "errors": null,
} satisfies PreviewInboundMapping200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PreviewInboundMapping200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


