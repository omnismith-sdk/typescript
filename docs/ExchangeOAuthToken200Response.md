
# ExchangeOAuthToken200Response


## Properties

Name | Type
------------ | -------------
`access_token` | string
`token_type` | string
`expires_in` | number
`refresh_token` | string
`scope` | string

## Example

```typescript
import type { ExchangeOAuthToken200Response } from '@omnismith-sdk/typescript'

// TODO: Update the object below with actual values
const example = {
  "access_token": eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCIsImtpZCI6IjAxOTVhOGYyYzNlNCJ9.eyJpc3MiOiJodHRwczovL2FwaS5vbW5pc21pdGguaW8iLCJzdWIiOiIwMTk1YThmMi1jM2U0LTcxMjMtODAwMC0wMDAwMDAwMDAwMDEiLCJhdWQiOiJvbW5pc21pdGgtYXBpIiwiaWF0IjoxNzI0Nzg4ODAwLCJleHAiOjE3MjQ3OTI0MDAsInByb2plY3RfaWQiOiIwMTk1YThmMi1jM2U0LTcxMjMtODAwMC0wMDAwMDAwMDAwMDEiLCJyb2xlX2lkIjoiMDE5NWE4ZjItYzNlNC03MTIzLTgwMDAtMDAwMDAwMDAwMDAyIiwicm9sZV9uYW1lIjoiT3duZXIiLCJpc19vd25lciI6dHJ1ZX0.signature,
  "token_type": Bearer,
  "expires_in": 3600,
  "refresh_token": omni_ort_0195a8f2c3e471238000000000000004,
  "scope": omnismith:all,
} satisfies ExchangeOAuthToken200Response

console.log(example)

// Convert the instance to a JSON string
const exampleJSON: string = JSON.stringify(example)
console.log(exampleJSON)

// Parse the JSON string back to an object
const exampleParsed = JSON.parse(exampleJSON) as ExchangeOAuthToken200Response
console.log(exampleParsed)
```

[[Back to top]](#) [[Back to API list]](../README.md#api-endpoints) [[Back to Model list]](../README.md#models) [[Back to README]](../README.md)


