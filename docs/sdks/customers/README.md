# Customers
(*customers*)

### Available Operations

* [create](#create) - Create a new customer.
* [findAll](#findall) - find All customers of an organization.
* [findOne](#findone) - find All customers of an organization.
* [updateCustomer](#updatecustomer) - Update a customer.
* [delete](#delete) - Delete a customer.

## create

Create a new customer.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.customers.create({
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

**Promise<[models.CreateCustomerResponse](../../models/createcustomerresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findAll

find All customers of an organization.

### Example Usage

```typescript
import { KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });

  const res = await sdk.customers.findAll();

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

**Promise<[models.FindAllCustomersResponse](../../models/findallcustomersresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## findOne

find All customers of an organization.

### Example Usage

```typescript
import { FindOneCustomerRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.customers.findOne(id);

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

**Promise<[models.FindOneCustomerResponse](../../models/findonecustomerresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## updateCustomer

Update a customer.

### Example Usage

```typescript
import { KohortPay, UpdateCustomerDto, UpdateCustomerRequest } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";
const updateCustomerDto: UpdateCustomerDto = {
  deletedAt: new Date("2021-07-22T00:00:00.000Z"),
};

  const res = await sdk.customers.updateCustomer(id, updateCustomerDto);

  if (res.statusCode == 200) {
    // handle response
  }
}

run();
```

### Parameters

| Parameter                                                     | Type                                                          | Required                                                      | Description                                                   |
| ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- | ------------------------------------------------------------- |
| `id`                                                          | *string*                                                      | :heavy_check_mark:                                            | N/A                                                           |
| `updateCustomerDto`                                           | [models.UpdateCustomerDto](../../models/updatecustomerdto.md) | :heavy_check_mark:                                            | N/A                                                           |
| `config`                                                      | [AxiosRequestConfig](https://axios-http.com/docs/req_config)  | :heavy_minus_sign:                                            | Available config options for making requests.                 |


### Response

**Promise<[models.UpdateCustomerResponse](../../models/updatecustomerresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |

## delete

Delete a customer.

### Example Usage

```typescript
import { DeleteCustomerRequest, KohortPay } from "kohortpay-node";

async function run() {
  const sdk = new KohortPay({
    bearer: "<YOUR_BEARER_TOKEN_HERE>",
  });
const id: string = "string";

  const res = await sdk.customers.delete(id);

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

**Promise<[models.DeleteCustomerResponse](../../models/deletecustomerresponse.md)>**
### Errors

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 400-600         | */*             |
