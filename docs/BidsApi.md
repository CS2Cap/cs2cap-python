# cs2cap.BidsApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**batch_bid_lookup**](BidsApi.md#batch_bid_lookup) | **POST** /v1/bids/batch | Batch Bid Lookup
[**list_bids**](BidsApi.md#list_bids) | **GET** /v1/bids | List Bids
[**stream_full_bids_snapshot**](BidsApi.md#stream_full_bids_snapshot) | **POST** /v1/bids | Stream Full Bids Snapshot


# **batch_bid_lookup**
> BatchBidsResponse batch_bid_lookup(batch_bids_request)

Batch Bid Lookup

Retrieve current bids (buy orders) for multiple items in a single request.

Maximum 100 items per request. Returns per-item bid quotes from each queried provider.

Prices are in minor units of the requested currency (e.g. USD cents when `currency=USD`). Divide by 100 for display.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.batch_bids_request import BatchBidsRequest
from cs2cap.models.batch_bids_response import BatchBidsResponse
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
    api_instance = cs2cap.BidsApi(api_client)
    batch_bids_request = cs2cap.BatchBidsRequest() # BatchBidsRequest | 

    try:
        # Batch Bid Lookup
        api_response = api_instance.batch_bid_lookup(batch_bids_request)
        print("The response of BidsApi->batch_bid_lookup:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling BidsApi->batch_bid_lookup: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **batch_bids_request** | [**BatchBidsRequest**](BatchBidsRequest.md)|  | 

### Return type

[**BatchBidsResponse**](BatchBidsResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Successful Response |  -  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Authenticated but not permitted to access this resource. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**400** | Batch size exceeded. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_bids**
> BidsResponse list_bids(item_id=item_id, market_hash_name=market_hash_name, phase=phase, providers=providers, currency=currency, limit=limit, offset=offset)

List Bids

Return current highest bids from providers that support buy orders.

Filters:
- `item_id` or `market_hash_name`
- optional `phase`
- `providers` limited to buy-order-capable provider keys
- `currency`, `limit`, and `offset`

Behavior:
- requesting a provider that does not support buy orders returns `400`

Response:
- `meta` with filters and providers queried
- flattened per-provider bid rows
- offset pagination metadata

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.bids_response import BidsResponse
from cs2cap.models.buy_order_provider import BuyOrderProvider
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
    api_instance = cs2cap.BidsApi(api_client)
    item_id = 56 # int | Filter by item ID. When provided, canonical market_hash_name and phase from catalog are used and take precedence over request market_hash_name/phase. (optional)
    market_hash_name = 'market_hash_name_example' # str | Optional market_hash_name to filter for specific item. Ignored when item_id is provided. (optional)
    phase = cs2cap.PhaseName() # PhaseName | Optional phase to filter (global or combined with market_hash_name). Ignored when item_id is provided. (optional)
    providers = [cs2cap.BuyOrderProvider()] # List[BuyOrderProvider] | Providers to include (provider-key enum values that support buy orders). Repeat `providers` to pass multiple values. (optional)
    currency = 'USD' # str | Target currency. Any ISO 4217 code supported by `/v1/fx` (see `/v1/fx` for the full list). Invalid codes return a 422 validation error. (optional) (default to 'USD')
    limit = 1000 # int | Maximum number of results to return. (optional) (default to 1000)
    offset = 0 # int | Number of results to skip for pagination. (optional) (default to 0)

    try:
        # List Bids
        api_response = api_instance.list_bids(item_id=item_id, market_hash_name=market_hash_name, phase=phase, providers=providers, currency=currency, limit=limit, offset=offset)
        print("The response of BidsApi->list_bids:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling BidsApi->list_bids: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **item_id** | **int**| Filter by item ID. When provided, canonical market_hash_name and phase from catalog are used and take precedence over request market_hash_name/phase. | [optional] 
 **market_hash_name** | **str**| Optional market_hash_name to filter for specific item. Ignored when item_id is provided. | [optional] 
 **phase** | [**PhaseName**](.md)| Optional phase to filter (global or combined with market_hash_name). Ignored when item_id is provided. | [optional] 
 **providers** | [**List[BuyOrderProvider]**](BuyOrderProvider.md)| Providers to include (provider-key enum values that support buy orders). Repeat &#x60;providers&#x60; to pass multiple values. | [optional] 
 **currency** | **str**| Target currency. Any ISO 4217 code supported by &#x60;/v1/fx&#x60; (see &#x60;/v1/fx&#x60; for the full list). Invalid codes return a 422 validation error. | [optional] [default to &#39;USD&#39;]
 **limit** | **int**| Maximum number of results to return. | [optional] [default to 1000]
 **offset** | **int**| Number of results to skip for pagination. | [optional] [default to 0]

### Return type

[**BidsResponse**](BidsResponse.md)

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
**400** | Providers were specified that do not support buy orders. |  -  |
**503** | Bid data is temporarily unavailable; retry shortly. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **stream_full_bids_snapshot**
> str stream_full_bids_snapshot(providers=providers)

Stream Full Bids Snapshot

Return the full live bids snapshot as an NDJSON stream.

Behavior:
- pro and quant tiers only
- requires an API key (not a session token)
- optional `providers` filter; omit to stream all providers
- fixed USD output
- `highest_bid` values are returned in USD minor units
- one JSON object per line using the `BuyOrderItem` field set
- per-API-key rolling 24h quota of successful stream starts (pro: 50, quant: 300, per endpoint)
- max 1 concurrent stream per API key for this endpoint (409 otherwise)

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.buy_order_provider import BuyOrderProvider
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
    api_instance = cs2cap.BidsApi(api_client)
    providers = [cs2cap.BuyOrderProvider()] # List[BuyOrderProvider] |  (optional)

    try:
        # Stream Full Bids Snapshot
        api_response = api_instance.stream_full_bids_snapshot(providers=providers)
        print("The response of BidsApi->stream_full_bids_snapshot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling BidsApi->stream_full_bids_snapshot: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **providers** | [**List[BuyOrderProvider]**](BuyOrderProvider.md)|  | [optional] 

### Return type

**str**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/x-ndjson, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | NDJSON stream of the full live bids snapshot in USD. |  * X-Snapshot-Timestamp - UTC timestamp when the snapshot stream started. <br>  * X-Snapshot-Currency - Fixed response currency for every streamed row. <br>  * X-Snapshot-Total - Total rows in the stream at start, when known. <br>  * X-RateLimit-Limit - Daily quota of successful stream starts for this endpoint. <br>  * X-RateLimit-Remaining - Remaining stream starts in the rolling 24h window. <br>  * X-RateLimit-Reset - Seconds until the oldest counted start leaves the window. <br>  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Bulk snapshot access requires a tier with bulk snapshot capability. |  -  |
**429** | Daily bulk stream quota exhausted for this API key. |  * Retry-After - Seconds until this API key may start another bids stream. <br>  * X-RateLimit-Limit - Daily quota of successful stream starts for this endpoint. <br>  * X-RateLimit-Remaining - Remaining stream starts in the rolling 24h window. <br>  * X-RateLimit-Reset - Seconds until the oldest counted start leaves the window. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**503** | Bid data is temporarily unavailable; retry shortly. |  -  |
**409** | A streaming request is already active for this API key. |  * Retry-After - Seconds to wait before retrying when present. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

