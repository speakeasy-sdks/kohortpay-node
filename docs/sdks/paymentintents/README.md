# PaymentIntents
(*paymentIntents*)

### Available Operations

* [create](#create) - Create a new Payment Intent
* [findAll](#findall) - Retrieve all Payment Intents
* [findOne](#findone) - Retrieve a Payment Intent by ID
* [cancel](#cancel) - Cancel a Payment Intent by ID

## create

Create a new Payment Intent

### Example Usage

```typescript
import { KohortPay, Status } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.paymentIntents.create({
    amount: 5000,
    checkoutSessionId: "cs_1abc2def3ghi",
    customerId: "cus_1abc2def3ghi",
    metadata: {},
    status: Status.RequiresPaymentMethod,
  });

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                               | Type                                                                    | Required                                                                | Description                                                             |
| ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| `request`                                                               | [models.CreatePaymentIntentDto](../../models/createpaymentintentdto.md) | :heavy_check_mark:                                                      | The request object to use for the request.                              |
| `config`                                                                | [AxiosRequestConfig](https://axios-http.com/docs/req_config)            | :heavy_minus_sign:                                                      | Available config options for making requests.                           |


### Response

**Promise<[models.CreatePaymentIntentResponse](../../models/createpaymentintentresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findAll

Retrieve all Payment Intents

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.paymentIntents.findAll();

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

**Promise<[models.FindAllPaymentIntentsResponse](../../models/findallpaymentintentsresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findOne

Retrieve a Payment Intent by ID

### Example Usage

```typescript
import { FindOnePaymentIntentRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.paymentIntents.findOne(id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_check_mark:                                           | ID of the Payment Intent to fetch                            |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.FindOnePaymentIntentResponse](../../models/findonepaymentintentresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## cancel

Cancel a Payment Intent by ID

### Example Usage

```typescript
import { CancelPaymentIntentRequest, CancelPaymentIntentSecurity, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay();
const id: string = "string";
const operationSecurity: CancelPaymentIntentSecurity = {
  bearer: "<YOUR_BEARER_TOKEN_HERE>",
};

  const res = await sdk.paymentIntents.cancel(operationSecurity, id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                                         | Type                                                                              | Required                                                                          | Description                                                                       |
| --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| `security`                                                                        | [models.CancelPaymentIntentSecurity](../../models/cancelpaymentintentsecurity.md) | :heavy_check_mark:                                                                | The security requirements to use for the request.                                 |
| `id`                                                                              | *string*                                                                          | :heavy_check_mark:                                                                | ID of the Payment Intent to cancel                                                |
| `config`                                                                          | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                      | :heavy_minus_sign:                                                                | Available config options for making requests.                                     |


### Response

**Promise<[models.CancelPaymentIntentResponse](../../models/cancelpaymentintentresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |
