<!-- Start SDK Example Usage [usage] -->
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
<!-- End SDK Example Usage [usage] -->