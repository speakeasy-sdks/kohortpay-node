# Customers
(*customers*)

### Available Operations

* [customersControllerFindAll](#customerscontrollerfindall) - find All customers of an organization.
* [customersControllerCreate](#customerscontrollercreate) - Create a new customer.
* [customersControllerRemove](#customerscontrollerremove)
* [customersControllerFindOne](#customerscontrollerfindone) - find All customers of an organization.
* [customersControllerUpdate](#customerscontrollerupdate)

## customersControllerFindAll

find All customers of an organization.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.customers.customersControllerFindAll();

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

**Promise<[models.CustomersControllerFindAllResponse](../../models/customerscontrollerfindallresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## customersControllerCreate

Create a new customer.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });

  const res = await sdk.customers.customersControllerCreate({
    emailAddress: "user@example.com",
    firstName: "John",
    lastName: "Doe",
    phoneNumber: "+1 555 555 5555",
    address: {
      addressLine1: " Avenue des Champs-Élysées",
      addressLine2: "Appartement 4B",
      city: "Paris",
      postalCode: "75014",
      country: "France",
      state: "Île-de-France",
    },
    shippingAddress: {
      addressLine1: " Avenue des Champs-Élysées",
      addressLine2: "Appartement 4B",
      city: "Paris",
      postalCode: "75014",
      country: "France",
      state: "Île-de-France",
    },
    metadata: {},
  });

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                     | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `request`                                                     | [models.CreateCustomerDto](../../models/createcustomerdto.md) | :heavy_check_mark:                                            | The request object to use for the request.                    |
| `config`                                                      | [AxiosRequestConfig](https://axios-http.com/docs/req_config)  | :heavy_minus_sign:                                            | Available config options for making requests.                 |


### Response

**Promise<[models.CustomersControllerCreateResponse](../../models/customerscontrollercreateresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## customersControllerRemove

### Example Usage

```typescript
import { CustomersControllerRemoveRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.customers.customersControllerRemove(id);

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

**Promise<[models.CustomersControllerRemoveResponse](../../models/customerscontrollerremoveresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## customersControllerFindOne

find All customers of an organization.

### Example Usage

```typescript
import { CustomersControllerFindOneRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";

  const res = await sdk.customers.customersControllerFindOne(id);

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

**Promise<[models.CustomersControllerFindOneResponse](../../models/customerscontrollerfindoneresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## customersControllerUpdate

### Example Usage

```typescript
import { CustomersControllerUpdateRequest, KohortPay, UpdateCustomerDto } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "",
  });
const id: string = "string";
const updateCustomerDto: UpdateCustomerDto = {
  deletedAt: new Date("2021-07-22T00:00:00.000Z"),
};

  const res = await sdk.customers.customersControllerUpdate(id, updateCustomerDto);

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
| `updateCustomerDto`                                          | [models.UpdateCustomerDto](../models/updatecustomerdto.md)   | :heavy_check_mark:                                           | N/A                                                          |
| `config`                                                     | [AxiosRequestConfig](https://axios-http.com/docs/req_config) | :heavy_minus_sign:                                           | Available config options for making requests.                |


### Response

**Promise<[models.CustomersControllerUpdateResponse](../../models/customerscontrollerupdateresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |
