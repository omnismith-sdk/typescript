
# SearchEntitiesRequest

Filter and global search criteria for querying template entities

## Properties

Name | Type
------------ | -------------
`global_search` | string
`filter_groups` | Array&lt;Array&lt;EntityFilter&gt;&gt;
`verbose` | boolean
`fields` | Array&lt;string&gt;

## Example

```typescript
import type { SearchEntitiesRequest } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "global_search": Wireless,
  "filter_groups": [[{"field":"status","operator":"in","value":["018b2f1b-8c1a-75b3-8000-7f0000010020"]},{"field":"price","operator":"gt","value":"100"}]],
  "verbose": false,
  "fields": ["title","status","scheduled_date"],
} satisfies SearchEntitiesRequest

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as SearchEntitiesRequest
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


