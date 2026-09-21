
# CreateWorkspaceViewRequest

Payload for adding a new view / pane to a workspace

## Properties

Name | Type
------------ | -------------
`template_id` | string
`name` | string
`filters` | Array&lt;object&gt;
`search_string` | string
`search_mode` | string
`sort` | [CreateWorkspaceViewRequestSort](CreateWorkspaceViewRequestSort.md)
`display_mode` | string
`displayed_columns` | Array&lt;string&gt;
`pane_order` | number

## Example

```typescript
import type { CreateWorkspaceViewRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "template_id": content_item,
  "name": Telegram Channel Hub,
  "filters": [{"field":"platform","operator":"eq","value":"telegram","is_active":true}],
  "search_string": manifesto,
  "search_mode": keyword,
  "sort": null,
  "display_mode": table,
  "displayed_columns": ["title","platform","status","scheduled_date"],
  "pane_order": 0,
} satisfies CreateWorkspaceViewRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as CreateWorkspaceViewRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


