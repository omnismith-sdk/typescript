
# EntityActionOverviewResponse

Template-scoped business action (e.g. status transition, workflow action).

## Properties

Name | Type
------------ | -------------
`id` | string
`slug` | string
`name` | string
`description` | string
`is_enabled` | boolean
`precondition` | [Array&lt;EntityRulePredicateOverviewResponse&gt;](EntityRulePredicateOverviewResponse.md)
`fields` | [Array&lt;EntityActionFieldOverviewResponse&gt;](EntityActionFieldOverviewResponse.md)
`presets` | [Array&lt;EntityActionPresetOverviewResponse&gt;](EntityActionPresetOverviewResponse.md)

## Example

```typescript
import type { EntityActionOverviewResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "id": 01a09900-0000-7000-8000-000000000001,
  "slug": resolve_ticket,
  "name": Resolve Ticket,
  "description": Marks the ticket as resolved,
  "is_enabled": true,
  "precondition": null,
  "fields": null,
  "presets": null,
} satisfies EntityActionOverviewResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as EntityActionOverviewResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


