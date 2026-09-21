
# UpdateEntityActionRequest


## Properties

Name | Type
------------ | -------------
`slug` | string
`name` | string
`description` | string
`icon` | string
`precondition` | [Array&lt;EntityRulePredicate&gt;](EntityRulePredicate.md)
`fields` | [Array&lt;EntityActionField&gt;](EntityActionField.md)
`presets` | [Array&lt;EntityActionPreset&gt;](EntityActionPreset.md)

## Example

```typescript
import type { UpdateEntityActionRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "slug": confirm_attendance,
  "name": Confirm attendance,
  "description": Marks the guest as confirmed and records the party size,
  "icon": check_circle,
  "precondition": null,
  "fields": null,
  "presets": null,
} satisfies UpdateEntityActionRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateEntityActionRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


