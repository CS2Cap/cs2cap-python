# cs2cap.PortfolioApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_item_to_portfolio**](PortfolioApi.md#add_item_to_portfolio) | **POST** /v1/portfolio/{portfolio_id}/items | Add Item to Portfolio
[**add_transaction**](PortfolioApi.md#add_transaction) | **POST** /v1/portfolio/{portfolio_id}/transactions | Add Transaction
[**create_portfolio**](PortfolioApi.md#create_portfolio) | **POST** /v1/portfolio | Create Portfolio
[**delete_portfolio**](PortfolioApi.md#delete_portfolio) | **DELETE** /v1/portfolio/{portfolio_id} | Delete Portfolio
[**delete_transaction**](PortfolioApi.md#delete_transaction) | **DELETE** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Delete Transaction
[**get_portfolio_value**](PortfolioApi.md#get_portfolio_value) | **GET** /v1/portfolio/{portfolio_id}/value | Get Portfolio Value
[**get_portfolio_value_history**](PortfolioApi.md#get_portfolio_value_history) | **GET** /v1/portfolio/{portfolio_id}/history | Get Portfolio Value History
[**import_steam_inventory**](PortfolioApi.md#import_steam_inventory) | **POST** /v1/portfolio/{portfolio_id}/import | Import Steam Inventory
[**list_portfolio_items**](PortfolioApi.md#list_portfolio_items) | **GET** /v1/portfolio/{portfolio_id}/items | List Portfolio Items
[**list_portfolios**](PortfolioApi.md#list_portfolios) | **GET** /v1/portfolio | List Portfolios
[**list_transactions**](PortfolioApi.md#list_transactions) | **GET** /v1/portfolio/{portfolio_id}/transactions | List Transactions
[**remove_item_from_portfolio**](PortfolioApi.md#remove_item_from_portfolio) | **DELETE** /v1/portfolio/{portfolio_id}/items/{entry_id} | Remove Item from Portfolio
[**update_transaction**](PortfolioApi.md#update_transaction) | **PATCH** /v1/portfolio/{portfolio_id}/transactions/{transaction_id} | Update Transaction
[**value_portfolio**](PortfolioApi.md#value_portfolio) | **POST** /v1/portfolio/value | Value Portfolio


# **add_item_to_portfolio**
> PortfolioItemOut add_item_to_portfolio(portfolio_id, portfolio_add_item_request)

Add Item to Portfolio

Add a single item to a portfolio by `item_id` or `market_hash_name`. Use this for manual entry without a Steam inventory import.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_add_item_request import PortfolioAddItemRequest
from cs2cap.models.portfolio_item_out import PortfolioItemOut
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    portfolio_add_item_request = cs2cap.PortfolioAddItemRequest() # PortfolioAddItemRequest | 

    try:
        # Add Item to Portfolio
        api_response = api_instance.add_item_to_portfolio(portfolio_id, portfolio_add_item_request)
        print("The response of PortfolioApi->add_item_to_portfolio:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->add_item_to_portfolio: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **portfolio_add_item_request** | [**PortfolioAddItemRequest**](PortfolioAddItemRequest.md)|  | 

### Return type

[**PortfolioItemOut**](PortfolioItemOut.md)

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
**400** | Missing item identifier. |  -  |
**404** | Portfolio or item not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **add_transaction**
> TransactionOut add_transaction(portfolio_id, transaction_create_request)

Add Transaction

Record a buy or sell transaction for an item in this portfolio.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.transaction_create_request import TransactionCreateRequest
from cs2cap.models.transaction_out import TransactionOut
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    transaction_create_request = cs2cap.TransactionCreateRequest() # TransactionCreateRequest | 

    try:
        # Add Transaction
        api_response = api_instance.add_transaction(portfolio_id, transaction_create_request)
        print("The response of PortfolioApi->add_transaction:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->add_transaction: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **transaction_create_request** | [**TransactionCreateRequest**](TransactionCreateRequest.md)|  | 

### Return type

[**TransactionOut**](TransactionOut.md)

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
**400** | Missing item identifier. |  -  |
**404** | Portfolio or item not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **create_portfolio**
> PortfolioOut create_portfolio(portfolio_create)

Create Portfolio

Create a new named portfolio. The maximum number of portfolios depends on your tier. Portfolios store items persistently and can be valued at any time.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_create import PortfolioCreate
from cs2cap.models.portfolio_out import PortfolioOut
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_create = cs2cap.PortfolioCreate() # PortfolioCreate | 

    try:
        # Create Portfolio
        api_response = api_instance.create_portfolio(portfolio_create)
        print("The response of PortfolioApi->create_portfolio:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->create_portfolio: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_create** | [**PortfolioCreate**](PortfolioCreate.md)|  | 

### Return type

[**PortfolioOut**](PortfolioOut.md)

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
**403** | Access denied. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**400** | Portfolio limit reached. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_portfolio**
> delete_portfolio(portfolio_id)

Delete Portfolio

Delete a portfolio and all its items.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # Delete Portfolio
        api_instance.delete_portfolio(portfolio_id)
    except Exception as e:
        print("Exception when calling PortfolioApi->delete_portfolio: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Authenticated but not permitted to access this resource. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_transaction**
> delete_transaction(portfolio_id, transaction_id)

Delete Transaction

Delete a transaction from a portfolio.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    transaction_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # Delete Transaction
        api_instance.delete_transaction(portfolio_id, transaction_id)
    except Exception as e:
        print("Exception when calling PortfolioApi->delete_transaction: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **transaction_id** | **UUID**|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Authenticated but not permitted to access this resource. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**404** | Portfolio or transaction not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_portfolio_value**
> PortfolioResponse get_portfolio_value(portfolio_id, currency=currency, providers=providers)

Get Portfolio Value

Value all items in a saved portfolio at live market prices. Items without price data appear in `items_not_found`. All money values are in minor units (e.g. USD cents). Divide by 100 for display.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_response import PortfolioResponse
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    currency = 'USD' # str | Target currency code. (optional) (default to 'USD')
    providers = ['providers_example'] # List[str] | Provider keys to include. Repeat to pass multiple, e.g. providers=steam&providers=skinport. Omit for all providers. (optional)

    try:
        # Get Portfolio Value
        api_response = api_instance.get_portfolio_value(portfolio_id, currency=currency, providers=providers)
        print("The response of PortfolioApi->get_portfolio_value:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->get_portfolio_value: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **currency** | **str**| Target currency code. | [optional] [default to &#39;USD&#39;]
 **providers** | [**List[str]**](str.md)| Provider keys to include. Repeat to pass multiple, e.g. providers&#x3D;steam&amp;providers&#x3D;skinport. Omit for all providers. | [optional] 

### Return type

[**PortfolioResponse**](PortfolioResponse.md)

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
**404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_portfolio_value_history**
> PortfolioHistoryPage get_portfolio_value_history(portfolio_id, start_date=start_date, end_date=end_date, lookback=lookback, currency=currency, providers=providers, limit=limit, cursor=cursor, basis=basis)

Get Portfolio Value History

Replay saved-portfolio holdings from the transaction ledger and return daily historical valuation points priced from stored daily market closes. This endpoint is daily-only because portfolio transactions are date-granular.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_history_page import PortfolioHistoryPage
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    start_date = '2013-10-20' # date | Inclusive UTC start date (YYYY-MM-DD). (optional)
    end_date = '2013-10-20' # date | Inclusive UTC end date (YYYY-MM-DD). Defaults to today. (optional)
    lookback = 'lookback_example' # str | Optional lookback in days, e.g. `30d`. Overrides start_date. (optional)
    currency = 'USD' # str | Target currency code. (optional) (default to 'USD')
    providers = ['providers_example'] # List[str] | Provider keys to include. Repeat to pass multiple, e.g. providers=steam&providers=skinport. Omit for all providers. (optional)
    limit = 56 # int | Maximum number of daily points to return. (optional)
    cursor = 'cursor_example' # str | Opaque cursor from `pagination.next_cursor`. (optional)
    basis = ledger # str | Holdings basis. `ledger` (default) replays holdings from the transaction ledger and requires recorded transactions. `holdings` values the portfolio's current holdings flat across the window, so history is available without any transactions. (optional) (default to ledger)

    try:
        # Get Portfolio Value History
        api_response = api_instance.get_portfolio_value_history(portfolio_id, start_date=start_date, end_date=end_date, lookback=lookback, currency=currency, providers=providers, limit=limit, cursor=cursor, basis=basis)
        print("The response of PortfolioApi->get_portfolio_value_history:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->get_portfolio_value_history: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **start_date** | **date**| Inclusive UTC start date (YYYY-MM-DD). | [optional] 
 **end_date** | **date**| Inclusive UTC end date (YYYY-MM-DD). Defaults to today. | [optional] 
 **lookback** | **str**| Optional lookback in days, e.g. &#x60;30d&#x60;. Overrides start_date. | [optional] 
 **currency** | **str**| Target currency code. | [optional] [default to &#39;USD&#39;]
 **providers** | [**List[str]**](str.md)| Provider keys to include. Repeat to pass multiple, e.g. providers&#x3D;steam&amp;providers&#x3D;skinport. Omit for all providers. | [optional] 
 **limit** | **int**| Maximum number of daily points to return. | [optional] 
 **cursor** | **str**| Opaque cursor from &#x60;pagination.next_cursor&#x60;. | [optional] 
 **basis** | **str**| Holdings basis. &#x60;ledger&#x60; (default) replays holdings from the transaction ledger and requires recorded transactions. &#x60;holdings&#x60; values the portfolio&#39;s current holdings flat across the window, so history is available without any transactions. | [optional] [default to ledger]

### Return type

[**PortfolioHistoryPage**](PortfolioHistoryPage.md)

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
**400** | Invalid window, invalid cursor, or no ledger history available. |  -  |
**404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **import_steam_inventory**
> PortfolioImportResult import_steam_inventory(portfolio_id, portfolio_import_request)

Import Steam Inventory

Import items from the user's Steam inventory into a portfolio. Optionally supply `asset_ids` to import only specific items. Items already present (by Steam asset ID) are skipped. Items not matched in the CS2C catalog are returned in `unresolved` and are not stored.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_import_request import PortfolioImportRequest
from cs2cap.models.portfolio_import_result import PortfolioImportResult
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    portfolio_import_request = cs2cap.PortfolioImportRequest() # PortfolioImportRequest | 

    try:
        # Import Steam Inventory
        api_response = api_instance.import_steam_inventory(portfolio_id, portfolio_import_request)
        print("The response of PortfolioApi->import_steam_inventory:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->import_steam_inventory: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **portfolio_import_request** | [**PortfolioImportRequest**](PortfolioImportRequest.md)|  | 

### Return type

[**PortfolioImportResult**](PortfolioImportResult.md)

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
**403** | No linked Steam account. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**404** | Portfolio not found. |  -  |
**503** | Steam inventory unavailable. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_portfolio_items**
> List[PortfolioItemOut] list_portfolio_items(portfolio_id)

List Portfolio Items

List all items in a saved portfolio.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_item_out import PortfolioItemOut
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # List Portfolio Items
        api_response = api_instance.list_portfolio_items(portfolio_id)
        print("The response of PortfolioApi->list_portfolio_items:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->list_portfolio_items: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 

### Return type

[**List[PortfolioItemOut]**](PortfolioItemOut.md)

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
**404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_portfolios**
> PortfolioListResponse list_portfolios()

List Portfolios

List all named portfolios belonging to the authenticated user.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_list_response import PortfolioListResponse
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
    api_instance = cs2cap.PortfolioApi(api_client)

    try:
        # List Portfolios
        api_response = api_instance.list_portfolios()
        print("The response of PortfolioApi->list_portfolios:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->list_portfolios: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**PortfolioListResponse**](PortfolioListResponse.md)

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
**403** | Access denied. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_transactions**
> List[TransactionOut] list_transactions(portfolio_id)

List Transactions

List all transactions in a portfolio, newest first.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.transaction_out import TransactionOut
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # List Transactions
        api_response = api_instance.list_transactions(portfolio_id)
        print("The response of PortfolioApi->list_transactions:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->list_transactions: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 

### Return type

[**List[TransactionOut]**](TransactionOut.md)

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
**404** | Portfolio not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **remove_item_from_portfolio**
> remove_item_from_portfolio(portfolio_id, entry_id)

Remove Item from Portfolio

Remove a specific item entry from a portfolio.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    entry_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # Remove Item from Portfolio
        api_instance.remove_item_from_portfolio(portfolio_id, entry_id)
    except Exception as e:
        print("Exception when calling PortfolioApi->remove_item_from_portfolio: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **entry_id** | **UUID**|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Successful Response |  -  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Authenticated but not permitted to access this resource. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**404** | Portfolio or item not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_transaction**
> TransactionOut update_transaction(portfolio_id, transaction_id, transaction_update_request)

Update Transaction

Partially update a transaction.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.transaction_out import TransactionOut
from cs2cap.models.transaction_update_request import TransactionUpdateRequest
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    transaction_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    transaction_update_request = cs2cap.TransactionUpdateRequest() # TransactionUpdateRequest | 

    try:
        # Update Transaction
        api_response = api_instance.update_transaction(portfolio_id, transaction_id, transaction_update_request)
        print("The response of PortfolioApi->update_transaction:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->update_transaction: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_id** | **UUID**|  | 
 **transaction_id** | **UUID**|  | 
 **transaction_update_request** | [**TransactionUpdateRequest**](TransactionUpdateRequest.md)|  | 

### Return type

[**TransactionOut**](TransactionOut.md)

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
**404** | Portfolio or transaction not found. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **value_portfolio**
> PortfolioResponse value_portfolio(portfolio_request)

Value Portfolio

Value an inventory of CS2 items at live market prices.

Send a list of `{item_id, quantity}` pairs and receive per-item valuation based on the best ask price across queried providers, plus a rolled-up total.

Maximum 100 distinct items per request.

All money values are in minor units of the requested currency (e.g. USD cents when `currency=USD`). Divide by 100 for display.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.portfolio_request import PortfolioRequest
from cs2cap.models.portfolio_response import PortfolioResponse
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
    api_instance = cs2cap.PortfolioApi(api_client)
    portfolio_request = cs2cap.PortfolioRequest() # PortfolioRequest | 

    try:
        # Value Portfolio
        api_response = api_instance.value_portfolio(portfolio_request)
        print("The response of PortfolioApi->value_portfolio:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling PortfolioApi->value_portfolio: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **portfolio_request** | [**PortfolioRequest**](PortfolioRequest.md)|  | 

### Return type

[**PortfolioResponse**](PortfolioResponse.md)

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

