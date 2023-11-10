# Authentication
(*authentication*)

## Overview

The authentication endpoints.

### Available Operations

* [login](#login) - Authenticate with the API by providing a username and password.

## login

Authenticate with the API by providing a username and password.

### Example Usage

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";
import { LoginSecurity, TypeT } from "The-Speakeasy-Bar/dist/sdk/models/operations";

(async() => {
  const sdk = new TheSpeakeasyBar();
const operationSecurity: LoginSecurity = {
  password: "<PASSWORD>",
  username: "<USERNAME>",
};

  const res = await sdk.authentication.login({
    type: TypeT.ApiKey,
  }, operationSecurity);

  if (res.statusCode == 200) {
    // handle response
  }
})();
```

### Parameters

| Parameter                                                                      | Type                                                                           | Required                                                                       | Description                                                                    |
| ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ | ------------------------------------------------------------------------------ |
| `request`                                                                      | [operations.LoginRequestBody](../../sdk/models/operations/loginrequestbody.md) | :heavy_check_mark:                                                             | The request object to use for the request.                                     |
| `security`                                                                     | [operations.LoginSecurity](../../sdk/models/operations/loginsecurity.md)       | :heavy_check_mark:                                                             | The security requirements to use for the request.                              |
| `config`                                                                       | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                   | :heavy_minus_sign:                                                             | Available config options for making requests.                                  |


### Response

**Promise<[operations.LoginResponse](../../sdk/models/operations/loginresponse.md)>**
### Errors

| Error Object     | Status Code      | Content Type     |
| ---------------- | ---------------- | ---------------- |
| errors.APIError  | 5XX              | application/json |
| errors.SDKError  | 400-600          | */*              |
