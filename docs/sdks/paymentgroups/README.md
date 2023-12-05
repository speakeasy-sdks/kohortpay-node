# PaymentGroups
(*paymentGroups*)

### Available Operations

* [paymentGroupsControllerFindAll](#paymentgroupscontrollerfindall) - Retrieve all payment groups
* [paymentGroupsControllerCreate](#paymentgroupscontrollercreate) - Create a new payment group
* [paymentGroupsControllerFindOne](#paymentgroupscontrollerfindone) - Retrieve a payment group by id
* [paymentGroupsControllerUpdate](#paymentgroupscontrollerupdate) - Update a payment group by id
* [paymentGroupsControllerParticipants](#paymentgroupscontrollerparticipants) - Retrieve participants of a payment group by id
* [paymentGroupsControllerCancel](#paymentgroupscontrollercancel) - Cancel a payment group by id
* [paymentGroupsControllerExpire](#paymentgroupscontrollerexpire) - Expire a payment group by id
* [paymentGroupsControllerValidate](#paymentgroupscontrollervalidate) - Validate a payment group by id

## paymentGroupsControllerFindAll

Retrieve all payment groups

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.paymentGroups.paymentGroupsControllerFindAll();

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

**Promise<[models.PaymentGroupsControllerFindAllResponse](../../models/paymentgroupscontrollerfindallresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## paymentGroupsControllerCreate

Create a new payment group

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.paymentGroups.paymentGroupsControllerCreate({
    customerId: "cus_IzkjlvAhdjzjht3",
    paymentIntentId: "pi_1JYLo8KerLxWZaQtys6ZQ1xR",
    metadata: {},
    expiresAt: new Date("2023-12-05T15:08:34.820Z"),
  });

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `request`                                                             | [models.CreatePaymentGroupDto](../../models/createpaymentgroupdto.md) | :heavy_check_mark:                                                    | The request object to use for the request.                            |
| `config`                                                              | [AxiosRequestConfig](https://axios-http.com/docs/req_config)          | :heavy_minus_sign:                                                    | Available config options for making requests.                         |


### Response

**Promise<[models.PaymentGroupsControllerCreateResponse](../../models/paymentgroupscontrollercreateresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## paymentGroupsControllerFindOne

Retrieve a payment group by id

### Example Usage

```typescript
import { KohortPay, PaymentGroupsControllerFindOneRequest } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.paymentGroupsControllerFindOne(id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_check_mark:                                           | N/A                                                          |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.PaymentGroupsControllerFindOneResponse](../../models/paymentgroupscontrollerfindoneresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## paymentGroupsControllerUpdate

Update a payment group by id

### Example Usage

```typescript
import {
  KohortPay,
  PaymentGroupsControllerUpdateRequest,
  UpdatePaymentGroupDto,
  UpdatePaymentGroupDtoMetadata,
} from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";
const updatePaymentGroupDto: UpdatePaymentGroupDto = {
  metadata: {},
};

  const res = await sdk.paymentGroups.paymentGroupsControllerUpdate(id, updatePaymentGroupDto);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                          | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `id`                                                               | *string*                                                           | :heavy_check_mark:                                                 | N/A                                                                |
| `updatePaymentGroupDto`                                            | [models.UpdatePaymentGroupDto](../models/updatepaymentgroupdto.md) | :heavy_check_mark:                                                 | N/A                                                                |
| `config`                                                           | [AxiosRequestConfig](https://axios-http.com/docs/req_config)       | :heavy_minus_sign:                                                 | Available config options for making requests.                      |


### Response

**Promise<[models.PaymentGroupsControllerUpdateResponse](../../models/paymentgroupscontrollerupdateresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## paymentGroupsControllerParticipants

Retrieve participants of a payment group by id

### Example Usage

```typescript
import { KohortPay, PaymentGroupsControllerParticipantsRequest } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.paymentGroupsControllerParticipants(id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_check_mark:                                           | N/A                                                          |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.PaymentGroupsControllerParticipantsResponse](../../models/paymentgroupscontrollerparticipantsresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## paymentGroupsControllerCancel

Cancel a payment group by id

### Example Usage

```typescript
import { KohortPay, PaymentGroupsControllerCancelRequest } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.paymentGroupsControllerCancel(id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_check_mark:                                           | N/A                                                          |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.PaymentGroupsControllerCancelResponse](../../models/paymentgroupscontrollercancelresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## paymentGroupsControllerExpire

Expire a payment group by id

### Example Usage

```typescript
import { KohortPay, PaymentGroupsControllerExpireRequest } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.paymentGroupsControllerExpire(id);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                    | Type                                                         | Required                                                     | Description                                                  |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| `id`                                                         | *string*                                                     | :heavy_check_mark:                                           | N/A                                                          |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.PaymentGroupsControllerExpireResponse](../../models/paymentgroupscontrollerexpireresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## paymentGroupsControllerValidate

Validate a payment group by id

### Example Usage

```typescript
import { KohortPay, PaymentGroupsControllerValidateRequest, ValidatePaymentGroupDto } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";
const validatePaymentGroupDto: ValidatePaymentGroupDto = {
  customerEmail: "customer@gmail.com",
};

  const res = await sdk.paymentGroups.paymentGroupsControllerValidate(id, validatePaymentGroupDto);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                              | Type                                                                   | Required                                                               | Description                                                            |
| ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `id`                                                                   | *string*                                                               | :heavy_check_mark:                                                     | N/A                                                                    |
| `validatePaymentGroupDto`                                              | [models.ValidatePaymentGroupDto](../models/validatepaymentgroupdto.md) | :heavy_check_mark:                                                     | N/A                                                                    |
| `config`                                                               | [AxiosRequestConfig](https://axios-http.com/docs/req_config)           | :heavy_minus_sign:                                                     | Available config options for making requests.                          |


### Response

**Promise<[models.PaymentGroupsControllerValidateResponse](../../models/paymentgroupscontrollervalidateresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |
