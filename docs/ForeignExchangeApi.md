# cs2cap.ForeignExchangeApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_fx_rates**](ForeignExchangeApi.md#get_fx_rates) | **GET** /v1/fx | Get FX Rates


# **get_fx_rates**
> FXRatesResponse get_fx_rates()

Get FX Rates

Return latest foreign exchange rates.

Parameters:
- None.

Response:
- `timestamp`: ISO timestamp for the rates snapshot.
- `rates`: Map of currency code to value relative to 1 USD (USD -> X).

Requirements:
- Valid API key with access to `/v1/fx`.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.fx_rates_response import FXRatesResponse
from cs2cap.rest import ApiException
from pprint import pprint

# Defining the host is optional and defaults to https://api.cs2c.app
# See configuration.py for a list of all supported configuration parameters.
configuration = cs2cap.Configuration(
    host = "https://api.cs2c.app"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure Bearer authorization: BearerAuth
configuration = cs2cap.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with cs2cap.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = cs2cap.ForeignExchangeApi(api_client)

    try:
        # Get FX Rates
        api_response = api_instance.get_fx_rates()
        print("The response of ForeignExchangeApi->get_fx_rates:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ForeignExchangeApi->get_fx_rates: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**FXRatesResponse**](FXRatesResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Authenticated but not permitted to access this resource. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

