# CreatePaymentIntentDto


## Fields

| Field                                          | Type                                           | Required                                       | Description                                    | Example                                        |
| ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- | ---------------------------------------------- |
| `amount`                                       | *number*                                       | :heavy_check_mark:                             | The amount to be charged.                      | 5000                                           |
| `checkoutSessionId`                            | *string*                                       | :heavy_check_mark:                             | Checkout Session id of the payment intent      | cs_1abc2def3ghi                                |
| `customerId`                                   | *string*                                       | :heavy_minus_sign:                             | Customer id of the payment intent              | cus_1abc2def3ghi                               |
| `metadata`                                     | [models.Metadata](../models/metadata.md)       | :heavy_minus_sign:                             | Additional metadata for the payment group.     | {<br/>"order_id": "ord_1JYLo8KerLxWZaQtys6ZQ1xS"<br/>} |
| `status`                                       | [models.Status](../models/status.md)           | :heavy_minus_sign:                             | Status of the payment intent                   | REQUIRES_PAYMENT_METHOD                        |