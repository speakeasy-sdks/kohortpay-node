# kohortPay

<div align="left">
    <a href="https://speakeasyapi.dev/"><img src="https://custom-icon-badges.demolab.com/badge/-Built%20By%20Speakeasy-212015?style=for-the-badge&logoColor=FBE331&logo=speakeasy&labelColor=545454" /></a>
    <a href="https://opensource.org/licenses/MIT">
        <img src="https://img.shields.io/badge/License-MIT-blue.svg" style="width: 100px; height: 28px;" />
    </a>
</div>



<!-- Start SDK Installation [installation] -->
## SDK Installation

### NPM

```bash
npm add kohortpay-node
```

### Yarn

```bash
yarn add kohortpay-node
```
<!-- End SDK Installation [installation] -->

<!-- Start SDK Example Usage [usage] -->
## SDK Example Usage

### Example

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
<!-- End SDK Example Usage [usage] -->

<!-- Start Available Resources and Operations [operations] -->
## Available Resources and Operations

### [paymentIntents](docs/sdks/paymentintents/README.md)

* [create](docs/sdks/paymentintents/README.md#create) - Create a new Payment Intent
* [findAll](docs/sdks/paymentintents/README.md#findall) - Retrieve all Payment Intents
* [findOne](docs/sdks/paymentintents/README.md#findone) - Retrieve a Payment Intent by ID
* [cancel](docs/sdks/paymentintents/README.md#cancel) - Cancel a Payment Intent by ID

### [paymentGroups](docs/sdks/paymentgroups/README.md)

* [create](docs/sdks/paymentgroups/README.md#create) - Create a new payment group
* [findAll](docs/sdks/paymentgroups/README.md#findall) - Retrieve all payment groups
* [findOne](docs/sdks/paymentgroups/README.md#findone) - Retrieve a payment group by id
* [update](docs/sdks/paymentgroups/README.md#update) - Update a payment group by id
* [getParticipants](docs/sdks/paymentgroups/README.md#getparticipants) - Retrieve participants of a payment group by id
* [cancel](docs/sdks/paymentgroups/README.md#cancel) - Cancel a payment group by id
* [expire](docs/sdks/paymentgroups/README.md#expire) - Expire a payment group by id
* [validatePaymentGroup](docs/sdks/paymentgroups/README.md#validatepaymentgroup) - Validate a payment group by id

### [customers](docs/sdks/customers/README.md)

* [create](docs/sdks/customers/README.md#create) - Create a new customer.
* [findAll](docs/sdks/customers/README.md#findall) - find All customers of an organization.
* [findOne](docs/sdks/customers/README.md#findone) - find All customers of an organization.
* [updateCustomer](docs/sdks/customers/README.md#updatecustomer) - Update a customer.
* [delete](docs/sdks/customers/README.md#delete) - Delete a customer.

### [checkoutSessions](docs/sdks/checkoutsessions/README.md)

* [create](docs/sdks/checkoutsessions/README.md#create) - Create a new checkout session.
* [findAll](docs/sdks/checkoutsessions/README.md#findall) - Retrieve all checkout sessions for the current organization and livemode.
* [findOne](docs/sdks/checkoutsessions/README.md#findone) - Retrieve a checkout session by ID for the current organization and livemode.
* [expire](docs/sdks/checkoutsessions/README.md#expire) - Expire a checkout session by ID for the current organization and livemode.
<!-- End Available Resources and Operations [operations] -->

<!-- Start Error Handling [errors] -->
## Error Handling

Handling errors in this SDK should largely match your expectations.  All operations return a response object or throw an error.  If Error objects are specified in your OpenAPI Spec, the SDK will throw the appropriate Error type.

| Error Object    | Status Code     | Content Type    |
| --------------- | --------------- | --------------- |
| models.SDKError | 4xx-5xx         | */*             |

Example

```typescript
import { KohortPay, Status } from "kohortpay-node";

async function run() {
    const sdk = new KohortPay({
        bearer: "<YOUR_BEARER_TOKEN_HERE>",
    });

    let res;
    try {
        res = await sdk.paymentIntents.create({
            amount: 5000,
            checkoutSessionId: "cs_1abc2def3ghi",
            customerId: "cus_1abc2def3ghi",
            metadata: {},
            status: Status.RequiresPaymentMethod,
        });
    } catch (err) {
        if (err instanceof models.SDKError) {
            console.error(err); // handle exception
            throw err;
        }
    }

    if (res.statusCode == 200) {
        // handle response
    }
}

run();

```
<!-- End Error Handling [errors] -->

<!-- Start Server Selection [server] -->
## Server Selection

### Select Server by Index

You can override the default server globally by passing a server index to the `serverIdx: number` optional parameter when initializing the SDK client instance. The selected server will then be used as the default on the operations that use it. This table lists the indexes associated with the available servers:

| # | Server | Variables |
| - | ------ | --------- |
| 0 | `https://api.kohortpay.com` | None |

#### Example

```typescript
import { KohortPay, Status } from "kohortpay-node";

async function run() {
    const sdk = new KohortPay({
        serverIdx: 0,
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


### Override Server URL Per-Client

The default server can also be overridden globally by passing a URL to the `serverURL: str` optional parameter when initializing the SDK client instance. For example:
```typescript
import { KohortPay, Status } from "kohortpay-node";

async function run() {
    const sdk = new KohortPay({
        serverURL: "https://api.kohortpay.com",
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
<!-- End Server Selection [server] -->

<!-- Start Custom HTTP Client [http-client] -->
## Custom HTTP Client

The Typescript SDK makes API calls using the [axios](https://axios-http.com/docs/intro) HTTP library.  In order to provide a convenient way to configure timeouts, cookies, proxies, custom headers, and other low-level configuration, you can initialize the SDK client with a custom `AxiosInstance` object.

For example, you could specify a header for every request that your sdk makes as follows:

```typescript
import { kohortpay-node } from "KohortPay";
import axios from "axios";

const httpClient = axios.create({
    headers: {'x-custom-header': 'someValue'}
})

const sdk = new KohortPay({defaultClient: httpClient});
```
<!-- End Custom HTTP Client [http-client] -->

<!-- Start Authentication [security] -->
## Authentication

### Per-Client Security Schemes

This SDK supports the following security scheme globally:

| Name        | Type        | Scheme      |
| ----------- | ----------- | ----------- |
| `bearer`    | http        | HTTP Bearer |

To authenticate with the API the `bearer` parameter must be set when initializing the SDK client instance. For example:
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

### Per-Operation Security Schemes

Some operations in this SDK require the security scheme to be specified at the request level. For example:
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
<!-- End Authentication [security] -->

<!-- Placeholder for Future Speakeasy SDK Sections -->

# Development

## Maturity

This SDK is in beta, and there may be breaking changes between versions without a major version update. Therefore, we recommend pinning usage
to a specific package version. This way, you can install the same version each time without breaking changes unless you are intentionally
looking for the latest version.

## Contributions

While we value open-source contributions to this SDK, this library is generated programmatically.
Feel free to open a PR or a Github issue as a proof of concept and we'll do our best to include it in a future release!

### SDK Created by [Speakeasy](https://docs.speakeasyapi.dev/docs/using-speakeasy/client-sdks)
