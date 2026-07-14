# cs2cap.MarketIntelligenceApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_arbitrage_opportunities**](MarketIntelligenceApi.md#get_arbitrage_opportunities) | **GET** /v1/market/arbitrage | Get Arbitrage Opportunities
[**get_deep_price_history_chart**](MarketIntelligenceApi.md#get_deep_price_history_chart) | **GET** /v1/market/history/chart | Get Deep Price History Chart
[**get_indicators**](MarketIntelligenceApi.md#get_indicators) | **GET** /v1/market/indicators | Get Indicators
[**get_item_analytics**](MarketIntelligenceApi.md#get_item_analytics) | **GET** /v1/market/items/{item_id} | Get Item Analytics
[**get_market_analytics_snapshot**](MarketIntelligenceApi.md#get_market_analytics_snapshot) | **GET** /v1/market/items | Get Market Analytics Snapshot
[**get_market_cap_indexes**](MarketIntelligenceApi.md#get_market_cap_indexes) | **GET** /v1/market/indexes | Get Market Cap Indexes


# **get_arbitrage_opportunities**
> MarketArbitrageResponse get_arbitrage_opportunities(limit=limit, offset=offset, min_spread_pct=min_spread_pct, providers_buy=providers_buy, providers_sell=providers_sell)

Get Arbitrage Opportunities

Scan providers for cross-market arbitrage opportunities.

Filters:
- `min_spread_pct`
- `providers_buy` and `providers_sell` (sell-side limited to buy-order providers)
- offset pagination via `offset`

Response:
- opportunities ranked by estimated net profit in USD with buy-side and sell-side provider context
- pagination total reflects the capped set of ranked opportunities, not a count of all possible matches

Tier: Quant-only.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.all_providers import AllProviders
from cs2cap.models.buy_order_provider import BuyOrderProvider
from cs2cap.models.market_arbitrage_response import MarketArbitrageResponse
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
    api_instance = cs2cap.MarketIntelligenceApi(api_client)
    limit = 56 # int | Maximum number of results to return. Defaults to the effective tier cap. (optional)
    offset = 0 # int | Requested offset into the ranked opportunity list. (optional) (default to 0)
    min_spread_pct = 1.0 # float | Minimum gross spread percentage between buy and sell prices. (optional) (default to 1.0)
    providers_buy = [cs2cap.AllProviders()] # List[AllProviders] | Buy-side provider key enum filters (plural parameter). Repeat `providers_buy` to pass multiple values. (optional)
    providers_sell = [cs2cap.BuyOrderProvider()] # List[BuyOrderProvider] | Sell-side provider key enum filters for providers with buy orders (plural parameter). Repeat `providers_sell` to pass multiple values. (optional)

    try:
        # Get Arbitrage Opportunities
        api_response = api_instance.get_arbitrage_opportunities(limit=limit, offset=offset, min_spread_pct=min_spread_pct, providers_buy=providers_buy, providers_sell=providers_sell)
        print("The response of MarketIntelligenceApi->get_arbitrage_opportunities:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MarketIntelligenceApi->get_arbitrage_opportunities: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Maximum number of results to return. Defaults to the effective tier cap. | [optional] 
 **offset** | **int**| Requested offset into the ranked opportunity list. | [optional] [default to 0]
 **min_spread_pct** | **float**| Minimum gross spread percentage between buy and sell prices. | [optional] [default to 1.0]
 **providers_buy** | [**List[AllProviders]**](AllProviders.md)| Buy-side provider key enum filters (plural parameter). Repeat &#x60;providers_buy&#x60; to pass multiple values. | [optional] 
 **providers_sell** | [**List[BuyOrderProvider]**](BuyOrderProvider.md)| Sell-side provider key enum filters for providers with buy orders (plural parameter). Repeat &#x60;providers_sell&#x60; to pass multiple values. | [optional] 

### Return type

[**MarketArbitrageResponse**](MarketArbitrageResponse.md)

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
**403** | Analytics tier required to access this endpoint. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**400** | Invalid cursor or unsupported cursor parameter. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_deep_price_history_chart**
> MarketHistoryChartResponse get_deep_price_history_chart(item_id=item_id, market_hash_name=market_hash_name, providers=providers, start=start, end=end, lookback=lookback, currency=currency, include_defunct=include_defunct)

Get Deep Price History Chart

Per-provider daily price history.

Returns one price point per provider per UTC day, spanning years of history
up to the present. Prices are in minor units of the response currency;
``qty`` is nullable.

Providers that have shut down are excluded by default; pass
``include_defunct=true`` to include their historical series.

**Tier**: Quant-only.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.market_history_chart_response import MarketHistoryChartResponse
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
    api_instance = cs2cap.MarketIntelligenceApi(api_client)
    item_id = 56 # int | Normalized catalog item ID (or use market_hash_name). (optional)
    market_hash_name = 'market_hash_name_example' # str | Market hash name (alternative to item_id). (optional)
    providers = ['providers_example'] # List[str] | Provider key(s). Repeatable. Omit for all providers with data. (optional)
    start = '2013-10-20T19:20:30+01:00' # datetime | ISO 8601 UTC start of the window. (optional)
    end = '2013-10-20T19:20:30+01:00' # datetime | ISO 8601 UTC end of the window. (optional)
    lookback = 56 # int | Window length in days; overrides start. (optional)
    currency = 'USD' # str | Target currency for returned prices. Default: USD. (optional) (default to 'USD')
    include_defunct = False # bool | Include providers that have shut down but still have historical data (e.g. GamerPay, BitSkins). Defaults to false. (optional) (default to False)

    try:
        # Get Deep Price History Chart
        api_response = api_instance.get_deep_price_history_chart(item_id=item_id, market_hash_name=market_hash_name, providers=providers, start=start, end=end, lookback=lookback, currency=currency, include_defunct=include_defunct)
        print("The response of MarketIntelligenceApi->get_deep_price_history_chart:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MarketIntelligenceApi->get_deep_price_history_chart: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **item_id** | **int**| Normalized catalog item ID (or use market_hash_name). | [optional] 
 **market_hash_name** | **str**| Market hash name (alternative to item_id). | [optional] 
 **providers** | [**List[str]**](str.md)| Provider key(s). Repeatable. Omit for all providers with data. | [optional] 
 **start** | **datetime**| ISO 8601 UTC start of the window. | [optional] 
 **end** | **datetime**| ISO 8601 UTC end of the window. | [optional] 
 **lookback** | **int**| Window length in days; overrides start. | [optional] 
 **currency** | **str**| Target currency for returned prices. Default: USD. | [optional] [default to &#39;USD&#39;]
 **include_defunct** | **bool**| Include providers that have shut down but still have historical data (e.g. GamerPay, BitSkins). Defaults to false. | [optional] [default to False]

### Return type

[**MarketHistoryChartResponse**](MarketHistoryChartResponse.md)

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
**403** | Analytics tier required to access this endpoint. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**400** | Invalid parameters |  -  |
**404** | Item not found |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_indicators**
> MarketIndicatorsItemResponse get_indicators(item_id=item_id, market_hash_name=market_hash_name, phase=phase, interval=interval, currency=currency)

Get Indicators

Compute technical analysis indicators for one item from OHLCV candle data.

**Indicators:**

- **Momentum**: RSI(14), MACD(12/26/9), SMA(20/50/200), EMA(12/26), Bollinger Bands(20,2σ)
- **Volatility**: ATR(14), Historical Volatility(20), Keltner Channels(20/10/2)
- **Volume**: VWAP, OBV, Volume SMA(20)

**Tier**: Quant-only.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.market_indicators_item_response import MarketIndicatorsItemResponse
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
    api_instance = cs2cap.MarketIntelligenceApi(api_client)
    item_id = 56 # int | Item ID for live indicator computation. (optional)
    market_hash_name = 'market_hash_name_example' # str | Market hash name (alternative to item_id). (optional)
    phase = 'phase_example' # str | Doppler phase filter. (optional)
    interval = 1d # str | Candle interval for indicator computation. (optional) (default to 1d)
    currency = 'USD' # str | Target currency for price-level indicators (e.g. ``USD``, ``EUR``). Provider-native prices are converted via FX rates. Default: ``USD``. (optional) (default to 'USD')

    try:
        # Get Indicators
        api_response = api_instance.get_indicators(item_id=item_id, market_hash_name=market_hash_name, phase=phase, interval=interval, currency=currency)
        print("The response of MarketIntelligenceApi->get_indicators:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MarketIntelligenceApi->get_indicators: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **item_id** | **int**| Item ID for live indicator computation. | [optional] 
 **market_hash_name** | **str**| Market hash name (alternative to item_id). | [optional] 
 **phase** | **str**| Doppler phase filter. | [optional] 
 **interval** | **str**| Candle interval for indicator computation. | [optional] [default to 1d]
 **currency** | **str**| Target currency for price-level indicators (e.g. &#x60;&#x60;USD&#x60;&#x60;, &#x60;&#x60;EUR&#x60;&#x60;). Provider-native prices are converted via FX rates. Default: &#x60;&#x60;USD&#x60;&#x60;. | [optional] [default to &#39;USD&#39;]

### Return type

[**MarketIndicatorsItemResponse**](MarketIndicatorsItemResponse.md)

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
**403** | Analytics tier required to access this endpoint. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Insufficient candle data for indicator computation |  -  |
**400** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_item_analytics**
> MarketItemAnalyticsResponse get_item_analytics(item_id)

Get Item Analytics

Return per-item market analytics across providers.

Includes:
- best ask, best bid, and spread summary
- item-level liquidity summary and provider-level price/depth/volume metrics
- coverage diagnostics showing which providers contributed data

Liquidity is always scored against the 24h horizon.
Provider volume fields are trailing 24h and 7d totals.

Tier: Pro and Quant.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.market_item_analytics_response import MarketItemAnalyticsResponse
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
    api_instance = cs2cap.MarketIntelligenceApi(api_client)
    item_id = 56 # int | Item ID.

    try:
        # Get Item Analytics
        api_response = api_instance.get_item_analytics(item_id)
        print("The response of MarketIntelligenceApi->get_item_analytics:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MarketIntelligenceApi->get_item_analytics: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **item_id** | **int**| Item ID. | 

### Return type

[**MarketItemAnalyticsResponse**](MarketItemAnalyticsResponse.md)

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
**403** | Analytics tier required to access this endpoint. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**404** | No analytics data exists for the provided item_id. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_market_analytics_snapshot**
> MarketItemsSnapshotResponse get_market_analytics_snapshot()

Get Market Analytics Snapshot

Return the full market as a summary-only snapshot.

Includes:
- one row per catalog item with the same summary fields exposed by the detail route
- no pagination and no provider-level payloads
- rank-ordered output using `rank asc, item_id asc`

Liquidity reflects the 24h horizon; trade windows are 24h, 7d, and 30d.

Tier: Pro and Quant.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.market_items_snapshot_response import MarketItemsSnapshotResponse
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
    api_instance = cs2cap.MarketIntelligenceApi(api_client)

    try:
        # Get Market Analytics Snapshot
        api_response = api_instance.get_market_analytics_snapshot()
        print("The response of MarketIntelligenceApi->get_market_analytics_snapshot:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MarketIntelligenceApi->get_market_analytics_snapshot: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**MarketItemsSnapshotResponse**](MarketItemsSnapshotResponse.md)

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
**403** | Analytics tier required to access this endpoint. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**503** | Market data is temporarily unavailable; retry shortly. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_market_cap_indexes**
> MarketIndexesResponse get_market_cap_indexes(group_by=group_by)

Get Market Cap Indexes

Aggregate the 24h market into category-level indexes.

Supports grouping by `item_type` or `weapon_type`.
Items are excluded from market cap totals when bid/ask/marketcap data is incomplete or spread exceeds the minimum threshold.

Response:
- no pagination
- groups sorted by `marketcap_usd desc`
- totals computed from the same filtered item set

Tier: Quant-only.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.market_indexes_response import MarketIndexesResponse
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
    api_instance = cs2cap.MarketIntelligenceApi(api_client)
    group_by = item_type # str | Catalog dimension used to group snapshot items. (optional) (default to item_type)

    try:
        # Get Market Cap Indexes
        api_response = api_instance.get_market_cap_indexes(group_by=group_by)
        print("The response of MarketIntelligenceApi->get_market_cap_indexes:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MarketIntelligenceApi->get_market_cap_indexes: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **group_by** | **str**| Catalog dimension used to group snapshot items. | [optional] [default to item_type]

### Return type

[**MarketIndexesResponse**](MarketIndexesResponse.md)

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
**403** | Analytics tier required to access this endpoint. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**503** | Market data is temporarily unavailable; retry shortly. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

