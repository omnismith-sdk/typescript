
# UpdateWorkspaceViewRequest

Payload for updating workspace view / pane configuration

## Properties

Name | Type
------------ | -------------
`name` | string
`filters` | Array&lt;object&gt;
`search_string` | string
`search_mode` | string
`sort` | [UpdateWorkspaceViewRequestSort](UpdateWorkspaceViewRequestSort.md)
`display_mode` | string
`displayed_columns` | Array&lt;string&gt;
`pane_order` | number

## Example

```typescript
import type { UpdateWorkspaceViewRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "name": Telegram Channel Hub,
  "filters": [{"field":"platform","operator":"eq","value":"telegram","is_active":true}],
  "search_string": manifesto,
  "search_mode": keyword,
  "sort": null,
  "display_mode": table,
  "displayed_columns": ["title","platform","status","scheduled_date"],
  "pane_order": 1,
} satisfies UpdateWorkspaceViewRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as UpdateWorkspaceViewRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


