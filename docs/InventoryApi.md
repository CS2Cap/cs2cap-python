# cs2cap.InventoryApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_steam_inventory**](InventoryApi.md#get_steam_inventory) | **GET** /v1/inventory/steam | Get Steam Inventory
[**get_steam_inventory_by_steam_id**](InventoryApi.md#get_steam_inventory_by_steam_id) | **GET** /v1/inventory/steam/lookup | Get Steam Inventory by Steam ID


# **get_steam_inventory**
> SteamInventoryResponse get_steam_inventory()

Get Steam Inventory

Fetch the authenticated user's live CS2 inventory from Steam. Requires a linked Steam account. No data is persisted — use the portfolio import endpoint to add items to a portfolio.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.steam_inventory_response import SteamInventoryResponse
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
    api_instance = cs2cap.InventoryApi(api_client)

    try:
        # Get Steam Inventory
        api_response = api_instance.get_steam_inventory()
        print("The response of InventoryApi->get_steam_inventory:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling InventoryApi->get_steam_inventory: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**SteamInventoryResponse**](SteamInventoryResponse.md)

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
**403** | No linked Steam account. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**503** | Steam inventory unavailable. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_steam_inventory_by_steam_id**
> SteamInventoryResponse get_steam_inventory_by_steam_id(steam_id)

Get Steam Inventory by Steam ID

Fetch the CS2 inventory for any Steam account by Steam64ID or vanity URL. Accepts a 17-digit Steam64ID (e.g. `76561197964243909`) or a custom URL name (e.g. `dadscap`). Vanity URL resolution requires a Steam Web API key to be configured. No data is persisted.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.steam_inventory_response import SteamInventoryResponse
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
    api_instance = cs2cap.InventoryApi(api_client)
    steam_id = 'steam_id_example' # str | Steam64ID (17-digit) or vanity URL name (e.g. 'dadscap').

    try:
        # Get Steam Inventory by Steam ID
        api_response = api_instance.get_steam_inventory_by_steam_id(steam_id)
        print("The response of InventoryApi->get_steam_inventory_by_steam_id:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling InventoryApi->get_steam_inventory_by_steam_id: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **steam_id** | **str**| Steam64ID (17-digit) or vanity URL name (e.g. &#39;dadscap&#39;). | 

### Return type

[**SteamInventoryResponse**](SteamInventoryResponse.md)

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
**400** | Steam ID could not be resolved. |  -  |
**503** | Steam inventory unavailable. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

