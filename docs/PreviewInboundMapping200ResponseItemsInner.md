
# PreviewInboundMapping200ResponseItemsInner


## Properties

Name | Type
------------ | -------------
`index` | number
`external_key` | string
`action` | string
`entity_id` | string
`attributes` | { [key: string]: any; }
`error` | { [key: string]: any; }

## Example

```typescript
import type { PreviewInboundMapping200ResponseItemsInner } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "index": null,
  "external_key": stripe:cus_1,
  "action": null,
  "entity_id": null,
  "attributes": null,
  "error": null,
} satisfies PreviewInboundMapping200ResponseItemsInner

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as PreviewInboundMapping200ResponseItemsInner
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


