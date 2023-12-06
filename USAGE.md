<!-- Start SDK Example Usage [usage] -->
### Sign in

First you need to send an authentication request to the API by providing your username and password.
In the request body, you should specify the type of token you would like to receive: API key or JSON Web Token.
If your credentials are valid, you will receive a token in the response object: `res.object.token: str`.

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";
import { LoginSecurity, TypeT } from "The-Speakeasy-Bar/dist/sdk/models/operations";

async function run() {
    const sdk = new TheSpeakeasyBar();
    const operationSecurity: LoginSecurity = {
        password: "<PASSWORD>",
        username: "<USERNAME>",
    };

    const res = await sdk.authentication.login(
        {
            type: TypeT.ApiKey,
        },
        operationSecurity
    );

    if (res.statusCode == 200) {
        // handle response
    }
}

run();

```

### Browse available drinks

Once you are authenticated, you can use the token you received for all other authenticated endpoints.
For example, you can filter the list of available drinks by type.

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

### Create an order

When you submit an order, you can include a callback URL along your request.
This URL will get called whenever the supplier updates the status of your order.

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";
import { OrderType } from "The-Speakeasy-Bar/dist/sdk/models/shared";

async function run() {
    const sdk = new TheSpeakeasyBar({
        security: {
            apiKey: "<YOUR_API_KEY>",
        },
    });

    const res = await sdk.orders.createOrder({
        requestBody: [
            {
                productCode: "APM-1F2D3",
                quantity: 26535,
                type: OrderType.Drink,
            },
        ],
    });

    if (res.statusCode == 200) {
        // handle response
    }
}

run();

```

### Subscribe to webhooks to receive stock updates

```typescript
import { TheSpeakeasyBar } from "The-Speakeasy-Bar";
import { Webhook } from "The-Speakeasy-Bar/dist/sdk/models/operations";

async function run() {
    const sdk = new TheSpeakeasyBar({
        security: {
            apiKey: "<YOUR_API_KEY>",
        },
    });

    const res = await sdk.config.subscribeToWebhooks([{}]);

    if (res.statusCode == 200) {
        // handle response
    }
}

run();

```
<!-- End SDK Example Usage [usage] -->