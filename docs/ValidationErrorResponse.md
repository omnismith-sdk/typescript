
# ValidationErrorResponse

RFC 7807 Validation Error Structure

## Properties

Name | Type
------------ | -------------
`type` | string
`title` | string
`status` | number
`errors` | { [key: string]: Array&lt;string&gt;; }
`detail` | string

## Example

```typescript
import type { ValidationErrorResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "type": error/validation,
  "title": Validation Failed,
  "status": 422,
  "errors": {"email":["This value is not a valid email address."]},
  "detail": email: This value is not a valid email address. See errors for details.,
} satisfies ValidationErrorResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ValidationErrorResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


