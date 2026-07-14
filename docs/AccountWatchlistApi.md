# cs2cap.AccountWatchlistApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_watchlist_entries**](AccountWatchlistApi.md#create_watchlist_entries) | **POST** /v1/account/watchlist | Create Watchlist Entries
[**delete_watchlist_entry**](AccountWatchlistApi.md#delete_watchlist_entry) | **DELETE** /v1/account/watchlist/{item_id} | Delete Watchlist Entry
[**list_watchlist**](AccountWatchlistApi.md#list_watchlist) | **GET** /v1/account/watchlist | List Watchlist


# **create_watchlist_entries**
> WatchlistCreateResponse create_watchlist_entries(watchlist_create_request)

Create Watchlist Entries

Save one or more normalized catalog items to the authenticated user's default watchlist.

Rules:
- accepts either a real API key or a session JWT bearer token
- send either `item_id` for a single add or `item_ids` for a batch add
- every item ID must exist in the API item catalog
- watchlist access and max saved items depend on the user's tier
- batch creates are all-or-nothing
- duplicate saves return `409`

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.watchlist_create_request import WatchlistCreateRequest
from cs2cap.models.watchlist_create_response import WatchlistCreateResponse
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
    api_instance = cs2cap.AccountWatchlistApi(api_client)
    watchlist_create_request = cs2cap.WatchlistCreateRequest() # WatchlistCreateRequest | 

    try:
        # Create Watchlist Entries
        api_response = api_instance.create_watchlist_entries(watchlist_create_request)
        print("The response of AccountWatchlistApi->create_watchlist_entries:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountWatchlistApi->create_watchlist_entries: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **watchlist_create_request** | [**WatchlistCreateRequest**](WatchlistCreateRequest.md)|  | 

### Return type

[**WatchlistCreateResponse**](WatchlistCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Successful Response |  -  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Authenticated but not permitted to access this resource. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_watchlist_entry**
> AccountMutationResponse delete_watchlist_entry(item_id)

Delete Watchlist Entry

Remove one saved watchlist entry by normalized `item_id`.

This path uses the catalog item ID, not the watchlist entry UUID.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.account_mutation_response import AccountMutationResponse
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
    api_instance = cs2cap.AccountWatchlistApi(api_client)
    item_id = 56 # int | 

    try:
        # Delete Watchlist Entry
        api_response = api_instance.delete_watchlist_entry(item_id)
        print("The response of AccountWatchlistApi->delete_watchlist_entry:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountWatchlistApi->delete_watchlist_entry: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **item_id** | **int**|  | 

### Return type

[**AccountMutationResponse**](AccountMutationResponse.md)

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

# **list_watchlist**
> WatchlistResponse list_watchlist(limit=limit, offset=offset, search=search)

List Watchlist

List saved watchlist items for the authenticated user.

Behavior:
- accepts either a real API key or a session JWT bearer token
- offset pagination ordered by newest saved first
- `search` matches exact numeric `item_id` or case-insensitive item-name substring
- response pagination includes a real `total` count

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.watchlist_response import WatchlistResponse
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
    api_instance = cs2cap.AccountWatchlistApi(api_client)
    limit = 50 # int | Requested page size. Values are clamped to the range 1..200. (optional) (default to 50)
    offset = 0 # int | Zero-based starting position for this page. (optional) (default to 0)
    search = 'search_example' # str | Exact numeric item_id match or case-insensitive market_hash_name substring. (optional)

    try:
        # List Watchlist
        api_response = api_instance.list_watchlist(limit=limit, offset=offset, search=search)
        print("The response of AccountWatchlistApi->list_watchlist:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountWatchlistApi->list_watchlist: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Requested page size. Values are clamped to the range 1..200. | [optional] [default to 50]
 **offset** | **int**| Zero-based starting position for this page. | [optional] [default to 0]
 **search** | **str**| Exact numeric item_id match or case-insensitive market_hash_name substring. | [optional] 

### Return type

[**WatchlistResponse**](WatchlistResponse.md)

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

