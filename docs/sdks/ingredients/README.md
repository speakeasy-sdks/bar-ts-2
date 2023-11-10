# Ingredients
(*ingredients*)

## Overview

The ingredients endpoints.

### Available Operations

* [listIngredients](#listingredients) - Get a list of ingredients.

## listIngredients

Get a list of ingredients, if authenticated this will include stock levels and product codes otherwise it will only include public information.

### Example Usage

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";

(async() => {
  const sdk = new TheSpeakeasyBar({
    security: {
      apiKey: "<YOUR_API_KEY>",
    },
  });

  const res = await sdk.ingredients.listIngredients({
    ingredients: [
      "string",
    ],
  });

  if (res.statusCode == 200) {
    // handle response
  }
})();
```

### Parameters

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `request`                                                                                  | [operations.ListIngredientsRequest](../../sdk/models/operations/listingredientsrequest.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `config`                                                                                   | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                               | :heavy_minus_sign:                                                                         | Available config options for making requests.                                              |


### Response

**Promise<[operations.ListIngredientsResponse](../../sdk/models/operations/listingredientsresponse.md)>**
### Errors

| Error Object     | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.APIError  | 5XX              | application/json |
| errors.SDKError  | 400-600          | */*              |
