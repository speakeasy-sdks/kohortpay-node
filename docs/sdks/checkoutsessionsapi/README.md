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
import { KohortPay } from "kohortPay";

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

**Promise<[operations.CheckoutSessionsControllerFindAllResponse](../../models/operations/checkoutsessionscontrollerfindallresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| errors.BadRequestResponse    | 400                          | application/json             |
| errors.UnauthorizedException | 401                          | application/json             |
| errors.ErrorT                | 404                          | application/json             |
| errors.SDKError              | 400-600                      | */*                          |

## checkoutSessionsControllerCreate

Create a new checkout session.

### Example Usage

```typescript
import { KohortPay } from "kohortPay";

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

| Parameter                                                                                  | Type                                                                                       | Required                                                                                   | Description                                                                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------ |
| `request`                                                                                  | [components.CreateCheckoutSessionDto](../../models/components/createcheckoutsessiondto.md) | :heavy_check_mark:                                                                         | The request object to use for the request.                                                 |
| `config`                                                                                   | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                               | :heavy_minus_sign:                                                                         | Available config options for making requests.                                              |


### Response

**Promise<[operations.CheckoutSessionsControllerCreateResponse](../../models/operations/checkoutsessionscontrollercreateresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| errors.BadRequestResponse    | 400                          | application/json             |
| errors.UnauthorizedException | 401                          | application/json             |
| errors.NotFoundException     | 404                          | application/json             |
| errors.SDKError              | 400-600                      | */*                          |

## checkoutSessionsControllerFindOne

Retrieve a checkout session by ID for the current organization and livemode.

### Example Usage

```typescript
import { KohortPay } from "kohortPay";
import { CheckoutSessionsControllerFindOneRequest } from "kohortPay/dist/models/operations";

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

**Promise<[operations.CheckoutSessionsControllerFindOneResponse](../../models/operations/checkoutsessionscontrollerfindoneresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| errors.UnauthorizedException | 401                          | application/json             |
| errors.NotFoundException     | 404                          | application/json             |
| errors.SDKError              | 400-600                      | */*                          |

## checkoutSessionsControllerExpire

Expire a checkout session by ID for the current organization and livemode.

### Example Usage

```typescript
import { KohortPay } from "kohortPay";
import { CheckoutSessionsControllerExpireRequest } from "kohortPay/dist/models/operations";

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

**Promise<[operations.CheckoutSessionsControllerExpireResponse](../../models/operations/checkoutsessionscontrollerexpireresponse.md)>**
### Errors

| Error Object                 | Status Code                  | Content Type                 |
| ---------------------------- | ---------------------------- | ---------------------------- |
| errors.UnauthorizedException | 401                          | application/json             |
| errors.BadRequestResponse    | 404                          | application/json             |
| errors.SDKError              | 400-600                      | */*                          |
