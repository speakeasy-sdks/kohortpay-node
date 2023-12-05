# CheckoutSessionsControllerExpireResponse


## Fields

| Field                                                              | Type                                                               | Required                                                           | Description                                                        |
| ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ | ------------------------------------------------------------------ |
| `contentType`                                                      | *string*                                                           | :heavy_check_mark:                                                 | HTTP response content type for this operation                      |
| `statusCode`                                                       | *number*                                                           | :heavy_check_mark:                                                 | HTTP response status code for this operation                       |
| `rawResponse`                                                      | [AxiosResponse](https://axios-http.com/docs/res_schema)            | :heavy_check_mark:                                                 | Raw HTTP response; suitable for custom response parsing            |
| `unauthorizedException`                                            | [models.UnauthorizedException](../models/unauthorizedexception.md) | :heavy_minus_sign:                                                 | API key is not Valid                                               |
| `badRequestResponse`                                               | [models.BadRequestResponse](../models/badrequestresponse.md)       | :heavy_minus_sign:                                                 | Checkout session not found.                                        |