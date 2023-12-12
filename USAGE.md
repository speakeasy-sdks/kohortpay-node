<!-- Start SDK Example Usage [usage] -->
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