# Omnismith TypeScript SDK

[![npm version](https://img.shields.io/npm/v/@omnismith-sdk%2Ftypescript)](https://www.npmjs.com/package/@omnismith-sdk/typescript)
[![PyPI version](https://img.shields.io/pypi/v/omnismith-sdk)](https://pypi.org/project/omnismith-sdk/)
[![Packagist version](https://img.shields.io/packagist/v/omnismith-sdk/php)](https://packagist.org/packages/omnismith-sdk/php)
[![Go Report Card](https://goreportcard.com/badge/github.com/omnismith-sdk/go)](https://goreportcard.com/report/github.com/omnismith-sdk/go)

The Omnismith TypeScript SDK is generated from the central OpenAPI contract for the [Omnismith platform](https://omnismith.io), a flexible data management system built around templates, entities, and attribute-driven schemas. Use it to automate workflows against the Omnismith API and pair it with the web app at [app.omnismith.io](https://app.omnismith.io).

## Quick Start

```typescript
import { Configuration, EntityApi, TemplatesApi } from "@omnismith-sdk/typescript";

const configuration = new Configuration({
  basePath: "https://api.omnismith.io/v1",
  accessToken: process.env.OMNISMITH_ACCESS_TOKEN,
});

const templatesApi = new TemplatesApi(configuration);
const entityApi = new EntityApi(configuration);

const templateId = "your-template-id";
const template = await templatesApi.getTemplate({ id: templateId });

const entity = await entityApi.createEntity({
  createEntityRequest: {
    template_id: template.id,
    attribute_values: [
      {
        attribute_id: template.attribute_ids[0],
        value: "SKU-1001",
      },
    ],
  },
});

console.log(template.name, entity.id);
```

Set `OMNISMITH_ACCESS_TOKEN` to an access token created in Omnismith before running the snippet.