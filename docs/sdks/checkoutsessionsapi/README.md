# CheckoutSessionsAPI
(*checkoutSessionsAPI*)

### Available Operations

* [checkoutSessionsControllerFindAll](#checkoutsessionscontrollerfindall) - Retrieve all checkout sessions for the current organization and livemode.
* [checkoutSessionsControllerCreate](#checkoutsessionscontrollercreate) - Create a new checkout session.
* [checkoutSessionsControllerFindOne](#checkoutsessionscontrollerfindone) - Retrieve a checkout session by ID for the current organization and livemode.
* [checkoutSessionsControllerExpire](#checkoutsessionscontrollerexpire) - Expire a checkout session by ID for the current organization and livemode.

## checkoutSessionsControllerFindAll

Retrieve all checkout sessions for the current organization and livemode.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.checkoutSessionsAPI.checkoutSessionsControllerFindAll();

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

**Promise<[models.CheckoutSessionsControllerFindAllResponse](../../models/checkoutsessionscontrollerfindallresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| models.BadRequestResponse    | 400                          | application/json             |
| models.UnauthorizedException | 401                          | application/json             |
| models.ErrorT                | 404                          | application/json             |
| models.SDKError              | 400-600                      | */*                          |

## checkoutSessionsControllerCreate

Create a new checkout session.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.checkoutSessionsAPI.checkoutSessionsControllerCreate({
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

**Promise<[models.CheckoutSessionsControllerCreateResponse](../../models/checkoutsessionscontrollercreateresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| models.BadRequestResponse    | 400                          | application/json             |
| models.UnauthorizedException | 401                          | application/json             |
| models.NotFoundException     | 404                          | application/json             |
| models.SDKError              | 400-600                      | */*                          |

## checkoutSessionsControllerFindOne

Retrieve a checkout session by ID for the current organization and livemode.

### Example Usage

```typescript
import { CheckoutSessionsControllerFindOneRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.checkoutSessionsAPI.checkoutSessionsControllerFindOne(id);

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

**Promise<[models.CheckoutSessionsControllerFindOneResponse](../../models/checkoutsessionscontrollerfindoneresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| models.UnauthorizedException | 401                          | application/json             |
| models.NotFoundException     | 404                          | application/json             |
| models.SDKError              | 400-600                      | */*                          |

## checkoutSessionsControllerExpire

Expire a checkout session by ID for the current organization and livemode.

### Example Usage

```typescript
import { CheckoutSessionsControllerExpireRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.checkoutSessionsAPI.checkoutSessionsControllerExpire(id);

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

**Promise<[models.CheckoutSessionsControllerExpireResponse](../../models/checkoutsessionscontrollerexpireresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| models.UnauthorizedException | 401                          | application/json             |
| models.BadRequestResponse    | 404                          | application/json             |
| models.SDKError              | 400-600                      | */*                          |
