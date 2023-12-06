# Drinks
(*drinks*)

## Overview

The drinks endpoints.

### Available Operations

* [getDrink](#getdrink) - Get a drink.
* [listDrinks](#listdrinks) - Get a list of drinks.

## getDrink

Get a drink by name, if authenticated this will include stock levels and product codes otherwise it will only include public information.

### Example Usage

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";

async function run() {
  const sdk = new TheSpeakeasyBar({
    security: {
      apiKey: "<YOUR_API_KEY>",
    },
  });

  const res = await sdk.drinks.getDrink({
    name: "string",
  });

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                                    | Type                                                                         | Required                                                                     | Description                                                                  |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------- |
| `request`                                                                    | [operations.GetDrinkRequest](../../sdk/models/operations/getdrinkrequest.md) | :heavy_check_mark:                                                           | The request object to use for the request.                                   |
| `config`                                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                 | :heavy_minus_sign:                                                           | Available config options for making requests.                                |


### Response

**Promise<[operations.GetDrinkResponse](../../sdk/models/operations/getdrinkresponse.md)>**
### Errors

| Error Object     | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.APIError  | 5XX              | application/json |
| errors.SDKError  | 400-600          | */*              |

## listDrinks

Get a list of drinks, if authenticated this will include stock levels and product codes otherwise it will only include public information.

### Example Usage

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";
import { DrinkType } from "The-Speakeasy-Bar/dist/sdk/models/shared";

async function run() {
  const sdk = new TheSpeakeasyBar({
    security: {
      apiKey: "<YOUR_API_KEY>",
    },
  });

  const res = await sdk.drinks.listDrinks({});

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                                        | Type                                                                             | Required                                                                         | Description                                                                      |
| -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| `request`                                                                        | [operations.ListDrinksRequest](../../sdk/models/operations/listdrinksrequest.md) | :heavy_check_mark:                                                               | The request object to use for the request.                                       |
| `serverURL`                                                                      | *string*                                                                         | :heavy_minus_sign:                                                               | An optional server URL to use.                                                   |
| `config`                                                                         | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                     | :heavy_minus_sign:                                                               | Available config options for making requests.                                    |


### Response

**Promise<[operations.ListDrinksResponse](../../sdk/models/operations/listdrinksresponse.md)>**
### Errors

| Error Object     | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.APIError  | 5XX              | application/json |
| errors.SDKError  | 400-600          | */*              |
