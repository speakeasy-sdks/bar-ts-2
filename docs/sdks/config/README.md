# Config
(*config*)

### Available Operations

* [subscribeToWebhooks](#subscribetowebhooks) - Subscribe to webhooks.

## subscribeToWebhooks

Subscribe to webhooks.

### Example Usage

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";
import { Webhook } from "The-Speakeasy-Bar/dist/sdk/models/operations";

async function run() {
  const sdk = new TheSpeakeasyBar({
    security: {
      apiKey: "<YOUR_API_KEY>",
    },
  });

  const res = await sdk.config.subscribeToWebhooks([
    {},
  ]);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                           | Type                                                                | Required                                                            | Description                                                         |
| ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- | ------------------------------------------------------------------- |
| `request`                                                           | [operations.RequestBody[]](../../models/.md)                        | :heavy_check_mark:                                                  | The request object to use for the request.                          |
| `retries`                                                           | [utils.RetryConfig](../../internal/utils/retryconfig.md)            | :heavy_minus_sign:                                                  | Configuration to override the default retry behavior of the client. |
| `config`                                                            | [AxiosRequestConfig](https://axios-http.com/docs/req_config)        | :heavy_minus_sign:                                                  | Available config options for making requests.                       |


### Response

**Promise<[operations.SubscribeToWebhooksResponse](../../sdk/models/operations/subscribetowebhooksresponse.md)>**
### Errors

| Error Object      | Status Code       | Content Type      |
| ----------------- | ----------------- | ----------------- |
| errors.BadRequest | 400               | application/json  |
| errors.APIError   | 5XX               | application/json  |
| errors.SDKError   | 400-600           | */*               |
