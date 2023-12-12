# PaymentGroups
(*paymentGroups*)

### Available Operations

* [create](#create) - Create a new payment group
* [findAll](#findall) - Retrieve all payment groups
* [findOne](#findone) - Retrieve a payment group by id
* [update](#update) - Update a payment group by id
* [getParticipants](#getparticipants) - Retrieve participants of a payment group by id
* [cancel](#cancel) - Cancel a payment group by id
* [expire](#expire) - Expire a payment group by id
* [validatePaymentGroup](#validatepaymentgroup) - Validate a payment group by id

## create

Create a new payment group

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.paymentGroups.create({
    customerId: "cus_IzkjlvAhdjzjht3",
    paymentIntentId: "pi_1JYLo8KerLxWZaQtys6ZQ1xR",
    metadata: {},
    expiresAt: new Date("2023-12-05T23:49:12.816Z"),
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

**Promise<[models.CreatePaymentGroupResponse](../../models/createpaymentgroupresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findAll

Retrieve all payment groups

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.paymentGroups.findAll();

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

**Promise<[models.FindAllPaymentGroupsResponse](../../models/findallpaymentgroupsresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findOne

Retrieve a payment group by id

### Example Usage

```typescript
import { FindOnePaymentGroupRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.findOne(id);

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

**Promise<[models.FindOnePaymentGroupResponse](../../models/findonepaymentgroupresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## update

Update a payment group by id

### Example Usage

```typescript
import { KohortPay, UpdatePaymentGroupDto, UpdatePaymentGroupDtoMetadata, UpdateRequest } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";
const updatePaymentGroupDto: UpdatePaymentGroupDto = {
  metadata: {},
};

  const res = await sdk.paymentGroups.update(id, updatePaymentGroupDto);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                             | Type                                                                  | Required                                                              | Description                                                           |
| --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------------------- |
| `id`                                                                  | *string*                                                              | :heavy_check_mark:                                                    | N/A                                                                   |
| `updatePaymentGroupDto`                                               | [models.UpdatePaymentGroupDto](../../models/updatepaymentgroupdto.md) | :heavy_check_mark:                                                    | N/A                                                                   |
| `config`                                                              | [AxiosRequestConfig](https://axios-http.com/docs/req_config)          | :heavy_minus_sign:                                                    | Available config options for making requests.                         |


### Response

**Promise<[models.UpdateResponse](../../models/updateresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## getParticipants

Retrieve participants of a payment group by id

### Example Usage

```typescript
import { GetParticipantsRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.getParticipants(id);

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

**Promise<[models.GetParticipantsResponse](../../models/getparticipantsresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## cancel

Cancel a payment group by id

### Example Usage

```typescript
import { CancelPaymentGroupRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.cancel(id);

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

**Promise<[models.CancelPaymentGroupResponse](../../models/cancelpaymentgroupresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## expire

Expire a payment group by id

### Example Usage

```typescript
import { ExpirePaymentGroupRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.paymentGroups.expire(id);

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

**Promise<[models.ExpirePaymentGroupResponse](../../models/expirepaymentgroupresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## validatePaymentGroup

Validate a payment group by id

### Example Usage

```typescript
import { KohortPay, ValidatePaymentGroupDto, ValidatePaymentGroupRequest } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";
const validatePaymentGroupDto: ValidatePaymentGroupDto = {
  customerEmail: "customer@gmail.com",
};

  const res = await sdk.paymentGroups.validatePaymentGroup(id, validatePaymentGroupDto);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                                 | Type                                                                      | Required                                                                  | Description                                                               |
| ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| `id`                                                                      | *string*                                                                  | :heavy_check_mark:                                                        | N/A                                                                       |
| `validatePaymentGroupDto`                                                 | [models.ValidatePaymentGroupDto](../../models/validatepaymentgroupdto.md) | :heavy_check_mark:                                                        | N/A                                                                       |
| `config`                                                                  | [AxiosRequestConfig](https://axios-http.com/docs/req_config)              | :heavy_minus_sign:                                                        | Available config options for making requests.                             |


### Response

**Promise<[models.ValidatePaymentGroupResponse](../../models/validatepaymentgroupresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |
