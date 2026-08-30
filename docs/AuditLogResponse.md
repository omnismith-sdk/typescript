
# AuditLogResponse

An immutable audit log entry recording a historical project mutation or action

## Properties

Name | Type
------------ | -------------
`event_id` | string
`occurred_at` | Date
`event_type` | string
`resource_type` | string
`resource_id` | string
`value` | string
`author_email` | string
`correlation_id` | string

## Example

```typescript
import type { AuditLogResponse } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "event_id": 018b2f1b-8c1a-75b3-8000-7f0000010000,
  "occurred_at": 2026-08-26T12:00Z,
  "event_type": entity.updated,
  "resource_type": entity,
  "resource_id": 018b2f1b-8c1a-75b3-8000-7f0000010001,
  "value": Updated attributes: price, status,
  "author_email": demo@omnismith.io,
  "correlation_id": corr-018b2f1b-8c1a-75b3,
} satisfies AuditLogResponse

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as AuditLogResponse
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


