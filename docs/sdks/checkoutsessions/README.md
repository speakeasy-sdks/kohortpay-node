# CheckoutSessions
(*checkoutSessions*)

### Available Operations

* [create](#create) - Create a new checkout session.
* [findAll](#findall) - Retrieve all checkout sessions for the current organization and livemode.
* [findOne](#findone) - Retrieve a checkout session by ID for the current organization and livemode.
* [expire](#expire) - Expire a checkout session by ID for the current organization and livemode.

## create

Create a new checkout session.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.checkoutSessions.create({
    successUrl: "https://success.example.com",
    cancelUrl: "https://cancel.example.com",
    customerEmail: "customer@example.com",
    customerFirstName: "John",
    customerLastName: "Doe",
    customerId: "user_xxxxxxxxxxxxxxxx",
    expiresAt: new Date("2023-10-02T14:30:00.000Z"),
    lineItems: [
      {
        name: "Item Name",
        price: 100,
        quantity: 1,
        imageUrl: "https://example.com/image.jpg",
        description: "Item Description",
        type: "PRODUCT",
      },
    ],
    metadata: {},
    amountTotal: 35000,
    locale: "en-US",
  });

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                                   | Type                                                                        | Required                                                                    | Description                                                                 |
| --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| `request`                                                                   | [models.CreateCheckoutSessionDto](../../models/createcheckoutsessiondto.md) | :heavy_check_mark:                                                          | The request object to use for the request.                                  |
| `config`                                                                    | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                | :heavy_minus_sign:                                                          | Available config options for making requests.                               |


### Response

**Promise<[models.CreateCheckoutResponse](../../models/createcheckoutresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findAll

Retrieve all checkout sessions for the current organization and livemode.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.checkoutSessions.findAll();

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.FindAllCheckoutSessionsResponse](../../models/findallcheckoutsessionsresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findOne

Retrieve a checkout session by ID for the current organization and livemode.

### Example Usage

```typescript
import { FindOneCheckoutSessionRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.checkoutSessions.findOne(id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_check_mark:                                           | ID of the checkout session to retrieve.                      |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.FindOneCheckoutSessionResponse](../../models/findonecheckoutsessionresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## expire

Expire a checkout session by ID for the current organization and livemode.

### Example Usage

```typescript
import { ExpireCheckoutSessionRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.checkoutSessions.expire(id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_check_mark:                                           | ID of the checkout session to expire.                        |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.ExpireCheckoutSessionResponse](../../models/expirecheckoutsessionresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |
