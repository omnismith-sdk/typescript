
# FileAttachmentResponse

File attachment details after upload

## Properties

Name | Type
------------ | -------------
`id` | string
`originalFilename` | string
`mimeType` | string
`size` | number

## Example

```typescript
import type { FileAttachmentResponse } from '@omnismith/sdk-typescript'

// TODO: Update the object below with actual values
const example = {
  "id": null,
  "originalFilename": null,
  "mimeType": null,
  "size": null,
} satisfies FileAttachmentResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as FileAttachmentResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


