# PaymentIntents
(*paymentIntents*)

### Available Operations

* [paymentIntentsControllerFindAll](#paymentintentscontrollerfindall) - Retrieve all Payment Intents
* [paymentIntentsControllerCreate](#paymentintentscontrollercreate) - Create a new Payment Intent
* [paymentIntentsControllerFindOne](#paymentintentscontrollerfindone) - Retrieve a Payment Intent by ID
* [paymentIntentsControllerCancel](#paymentintentscontrollercancel) - Cancel a Payment Intent by ID

## paymentIntentsControllerFindAll

Retrieve all Payment Intents

### Example Usage

```typescript
import { KohortPay } from "kohortPay";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.paymentIntents.paymentIntentsControllerFindAll();

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

**Promise<[operations.PaymentIntentsControllerFindAllResponse](../../models/operations/paymentintentscontrollerfindallresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 400-600         | */*             |

## paymentIntentsControllerCreate

Create a new Payment Intent

### Example Usage

```typescript
import { KohortPay } from "kohortPay";
import { Status } from "kohortPay/dist/models/components";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.paymentIntents.paymentIntentsControllerCreate({
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

| Parameter                                                                              | Type                                                                                   | Required                                                                               | Description                                                                            |
| -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------- |
| `request`                                                                              | [components.CreatePaymentIntentDto](../../models/components/createpaymentintentdto.md) | :heavy_check_mark:                                                                     | The request object to use for the request.                                             |
| `config`                                                                               | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                           | :heavy_minus_sign:                                                                     | Available config options for making requests.                                          |


### Response

**Promise<[operations.PaymentIntentsControllerCreateResponse](../../models/operations/paymentintentscontrollercreateresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 400-600         | */*             |

## paymentIntentsControllerFindOne

Retrieve a Payment Intent by ID

### Example Usage

```typescript
import { KohortPay } from "kohortPay";
import { PaymentIntentsControllerFindOneRequest } from "kohortPay/dist/models/operations";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.paymentIntents.paymentIntentsControllerFindOne(id);

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

**Promise<[operations.PaymentIntentsControllerFindOneResponse](../../models/operations/paymentintentscontrollerfindoneresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 400-600         | */*             |

## paymentIntentsControllerCancel

Cancel a Payment Intent by ID

### Example Usage

```typescript
import { KohortPay } from "kohortPay";
import { PaymentIntentsControllerCancelRequest, PaymentIntentsControllerCancelSecurity } from "kohortPay/dist/models/operations";

async function run() {
  const sdk = new KohortPay();
const id: string = "string";
const operationSecurity: PaymentIntentsControllerCancelSecurity = {
  bearer: "",
};

  const res = await sdk.paymentIntents.paymentIntentsControllerCancel(operationSecurity, id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                                                                              | Type                                                                                                                   | Required                                                                                                               | Description                                                                                                            |
| ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `security`                                                                                                             | [operations.PaymentIntentsControllerCancelSecurity](../../models/operations/paymentintentscontrollercancelsecurity.md) | :heavy_check_mark:                                                                                                     | The security requirements to use for the request.                                                                      |
| `id`                                                                                                                   | *string*                                                                                                               | :heavy_check_mark:                                                                                                     | ID of the Payment Intent to cancel                                                                                     |
| `config`                                                                                                               | [AxiosRequestConfig](https://axios-http.com/docs/req_config)                                                           | :heavy_minus_sign:                                                                                                     | Available config options for making requests.                                                                          |


### Response

**Promise<[operations.PaymentIntentsControllerCancelResponse](../../models/operations/paymentintentscontrollercancelresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| errors.SDKError | 400-600         | */*             |
