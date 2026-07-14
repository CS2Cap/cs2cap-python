# cs2cap.SalesApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_recent_sales**](SalesApi.md#list_recent_sales) | **GET** /v1/sales | List Recent Sales


# **list_recent_sales**
> SalesHistoryResponse list_recent_sales(item_id=item_id, market_hash_name=market_hash_name, phase=phase, providers=providers, min_float=min_float, max_float=max_float, paint_seed=paint_seed, stickers=stickers, charms=charms, currency=currency, limit=limit, cursor=cursor)

List Recent Sales

Return recent sales across providers with recent-sales support, newest first.

With no filters, returns the global recent-sales feed ordered by sale time (most recent first). Optional filters narrow the results:
- `item_id` — restrict to one catalog item (its canonical market_hash_name and phase are used)
- `market_hash_name` (+ optional `phase`) — restrict to one item by name
- `min_float` / `max_float` — restrict to a float-value range
- `paint_seed` — restrict to an exact paint seed
- `stickers` — restrict to sales containing every requested sticker name
- `charms` — restrict to sales containing one requested charm name
- `providers` — restrict to specific sales-capable provider keys
- `currency` — convert values to the target currency

Pagination:
- `limit` sets the page size (max 100 for Pro, 1000 for Quant)
- pass `cursor` from the previous response's `pagination.next_cursor` to page through results; `pagination.total` is `-1` (count intentionally skipped)

Behavior:
- recent-sales data refreshes roughly once every 24 hours, so results may be up to a day old

Response:
- request metadata, providers queried, and a cursor pagination footer
- sales records with sticker, charm, and inspect metadata when available

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.recent_sales_provider import RecentSalesProvider
from cs2cap.models.sales_history_response import SalesHistoryResponse
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
    api_instance = cs2cap.SalesApi(api_client)
    item_id = 56 # int | Filter by item ID. When provided, canonical market_hash_name and phase from catalog are used and take precedence over request market_hash_name/phase. (optional)
    market_hash_name = 'market_hash_name_example' # str | Optional market_hash_name to filter for specific item. Ignored when item_id is provided. (optional)
    phase = cs2cap.PhaseName() # PhaseName | Optional phase to filter (global or combined with market_hash_name). Ignored when item_id is provided. (optional)
    providers = [cs2cap.RecentSalesProvider()] # List[RecentSalesProvider] | Providers to include (provider-key enum values that support recent sales). Repeat `providers` to pass multiple values. (optional)
    min_float = 3.4 # float | Inclusive minimum item float value to include. (optional)
    max_float = 3.4 # float | Inclusive maximum item float value to include. (optional)
    paint_seed = 56 # int | Exact paint seed value to include. (optional)
    stickers = ['stickers_example'] # List[str] | Sticker names to require on returned sales. Repeat `stickers` to require multiple names. (optional)
    charms = 'charms_example' # str | Charm/keychain name to require on returned sales. Only one `charms` value is allowed. (optional)
    currency = 'USD' # str | Target currency. Any ISO 4217 code supported by `/v1/fx` (see `/v1/fx` for the full list). Invalid codes return a 422 validation error. (optional) (default to 'USD')
    limit = 56 # int | Maximum number of results to return. Defaults to the effective tier cap. (optional)
    cursor = 'cursor_example' # str | Cursor for keyset pagination. Use next_cursor from previous response. When provided, offset is ignored and keyset pagination is used for O(1) seek. (optional)

    try:
        # List Recent Sales
        api_response = api_instance.list_recent_sales(item_id=item_id, market_hash_name=market_hash_name, phase=phase, providers=providers, min_float=min_float, max_float=max_float, paint_seed=paint_seed, stickers=stickers, charms=charms, currency=currency, limit=limit, cursor=cursor)
        print("The response of SalesApi->list_recent_sales:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling SalesApi->list_recent_sales: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **item_id** | **int**| Filter by item ID. When provided, canonical market_hash_name and phase from catalog are used and take precedence over request market_hash_name/phase. | [optional] 
 **market_hash_name** | **str**| Optional market_hash_name to filter for specific item. Ignored when item_id is provided. | [optional] 
 **phase** | [**PhaseName**](.md)| Optional phase to filter (global or combined with market_hash_name). Ignored when item_id is provided. | [optional] 
 **providers** | [**List[RecentSalesProvider]**](RecentSalesProvider.md)| Providers to include (provider-key enum values that support recent sales). Repeat &#x60;providers&#x60; to pass multiple values. | [optional] 
 **min_float** | **float**| Inclusive minimum item float value to include. | [optional] 
 **max_float** | **float**| Inclusive maximum item float value to include. | [optional] 
 **paint_seed** | **int**| Exact paint seed value to include. | [optional] 
 **stickers** | [**List[str]**](str.md)| Sticker names to require on returned sales. Repeat &#x60;stickers&#x60; to require multiple names. | [optional] 
 **charms** | **str**| Charm/keychain name to require on returned sales. Only one &#x60;charms&#x60; value is allowed. | [optional] 
 **currency** | **str**| Target currency. Any ISO 4217 code supported by &#x60;/v1/fx&#x60; (see &#x60;/v1/fx&#x60; for the full list). Invalid codes return a 422 validation error. | [optional] [default to &#39;USD&#39;]
 **limit** | **int**| Maximum number of results to return. Defaults to the effective tier cap. | [optional] 
 **cursor** | **str**| Cursor for keyset pagination. Use next_cursor from previous response. When provided, offset is ignored and keyset pagination is used for O(1) seek. | [optional] 

### Return type

[**SalesHistoryResponse**](SalesHistoryResponse.md)

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
**400** | Invalid cursor or unsupported provider selection. |  -  |
**404** | The requested item could not be resolved. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

