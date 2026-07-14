# cs2cap.AccountAlertsApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_alert**](AccountAlertsApi.md#create_alert) | **POST** /v1/account/alerts | Create Alert
[**create_alerts_batch**](AccountAlertsApi.md#create_alerts_batch) | **POST** /v1/account/alerts/batch | Create Alerts Batch
[**delete_alert**](AccountAlertsApi.md#delete_alert) | **DELETE** /v1/account/alerts/{alert_id} | Delete Alert
[**list_alert_events**](AccountAlertsApi.md#list_alert_events) | **GET** /v1/account/alerts/events | List Alert Events
[**list_alerts**](AccountAlertsApi.md#list_alerts) | **GET** /v1/account/alerts | List Alerts
[**update_alert**](AccountAlertsApi.md#update_alert) | **PATCH** /v1/account/alerts/{alert_id} | Update Alert


# **create_alert**
> AlertDefinition create_alert(alert_create_request)

Create Alert

Create a new item-scoped account alert.

Supported kinds:
- `price_below`: trigger when the current best ask is at or below the threshold
- `price_above`: trigger when the current best ask is at or above the threshold
- `spread_exceeds`: trigger when `((best_ask - best_bid) / best_ask) * 100` meets or exceeds the threshold

Rules:
- accepts either a real API key or a session JWT bearer token
- `spread_exceeds` ignores `threshold_currency`
- price alerts default `threshold_currency` to the account preferred currency when omitted; accounts that have not set a preference use USD
- enabled alerts require at least one configured delivery channel (verified email delivery or an active webhook destination)
- the active enabled-alert cap is tier-controlled

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.alert_create_request import AlertCreateRequest
from cs2cap.models.alert_definition import AlertDefinition
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
    api_instance = cs2cap.AccountAlertsApi(api_client)
    alert_create_request = cs2cap.AlertCreateRequest() # AlertCreateRequest | 

    try:
        # Create Alert
        api_response = api_instance.create_alert(alert_create_request)
        print("The response of AccountAlertsApi->create_alert:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAlertsApi->create_alert: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **alert_create_request** | [**AlertCreateRequest**](AlertCreateRequest.md)|  | 

### Return type

[**AlertDefinition**](AlertDefinition.md)

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

# **create_alerts_batch**
> AlertBatchCreateResponse create_alerts_batch(alert_batch_create_request)

Create Alerts Batch

Create multiple item-scoped account alerts in one request.

Rules:
- accepts either a real API key or a session JWT bearer token
- maximum 100 alerts per request
- gated by the `batch_alert_creation_access` feature flag
- enabled alerts are preflight-checked against the tier active-alert cap before inserts
- exact duplicate alert payloads in the same request are rejected inline
- the response preserves request order and reports per-item created/error status
- the request consumes one API call regardless of batch size

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.alert_batch_create_request import AlertBatchCreateRequest
from cs2cap.models.alert_batch_create_response import AlertBatchCreateResponse
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
    api_instance = cs2cap.AccountAlertsApi(api_client)
    alert_batch_create_request = cs2cap.AlertBatchCreateRequest() # AlertBatchCreateRequest | 

    try:
        # Create Alerts Batch
        api_response = api_instance.create_alerts_batch(alert_batch_create_request)
        print("The response of AccountAlertsApi->create_alerts_batch:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAlertsApi->create_alerts_batch: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **alert_batch_create_request** | [**AlertBatchCreateRequest**](AlertBatchCreateRequest.md)|  | 

### Return type

[**AlertBatchCreateResponse**](AlertBatchCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Batch processed successfully. |  -  |
**401** | Missing or invalid authentication credentials. |  -  |
**403** | Batch alert creation is not available for this tier. |  -  |
**429** | Rate limit exceeded (burst or monthly quota). |  * Retry-After - Seconds to wait before retrying when present. <br>  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  * X-RateLimit-Limit - Request limit for the rate-limit window that was exceeded. <br>  * X-RateLimit-Remaining - Remaining requests in the rate-limit window that was exceeded. <br>  * X-RateLimit-Reset - Seconds until the rate-limit window resets. <br>  |
**422** | Request validation failed. The detail list contains field-specific validation errors. |  * X-RateLimit-Tier - Authenticated caller tier code when available. <br>  |
**400** | Batch size exceeded. |  -  |
**402** | Enabled-alert cap would be exceeded by this batch. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_alert**
> AccountMutationResponse delete_alert(alert_id)

Delete Alert

Delete one alert definition owned by the authenticated user.

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
    api_instance = cs2cap.AccountAlertsApi(api_client)
    alert_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 

    try:
        # Delete Alert
        api_response = api_instance.delete_alert(alert_id)
        print("The response of AccountAlertsApi->delete_alert:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAlertsApi->delete_alert: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **alert_id** | **UUID**|  | 

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

# **list_alert_events**
> AlertEventsResponse list_alert_events(limit=limit, offset=offset)

List Alert Events

List recent alert trigger events and delivery attempts for the authenticated user.

Behavior:
- accepts either a real API key or a session JWT bearer token
- offset pagination ordered by newest event first
- delivery rows currently reflect email delivery attempts

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.alert_events_response import AlertEventsResponse
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
    api_instance = cs2cap.AccountAlertsApi(api_client)
    limit = 50 # int | Requested page size. Values are clamped to the range 1..100. (optional) (default to 50)
    offset = 0 # int | Requested offset into the event history. (optional) (default to 0)

    try:
        # List Alert Events
        api_response = api_instance.list_alert_events(limit=limit, offset=offset)
        print("The response of AccountAlertsApi->list_alert_events:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAlertsApi->list_alert_events: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Requested page size. Values are clamped to the range 1..100. | [optional] [default to 50]
 **offset** | **int**| Requested offset into the event history. | [optional] [default to 0]

### Return type

[**AlertEventsResponse**](AlertEventsResponse.md)

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

# **list_alerts**
> AlertListResponse list_alerts(limit=limit, offset=offset, search=search)

List Alerts

List configured item alerts for the authenticated user.

Behavior:
- accepts either a real API key or a session JWT bearer token
- offset pagination ordered by newest created first
- `search` matches exact numeric `item_id` or case-insensitive item-name substring
- response pagination includes a real `total` count

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.alert_list_response import AlertListResponse
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
    api_instance = cs2cap.AccountAlertsApi(api_client)
    limit = 50 # int | Requested page size. Values are clamped to the range 1..200. (optional) (default to 50)
    offset = 0 # int | Zero-based starting position for this page. (optional) (default to 0)
    search = 'search_example' # str | Exact numeric item_id match or case-insensitive market_hash_name substring. (optional)

    try:
        # List Alerts
        api_response = api_instance.list_alerts(limit=limit, offset=offset, search=search)
        print("The response of AccountAlertsApi->list_alerts:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAlertsApi->list_alerts: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Requested page size. Values are clamped to the range 1..200. | [optional] [default to 50]
 **offset** | **int**| Zero-based starting position for this page. | [optional] [default to 0]
 **search** | **str**| Exact numeric item_id match or case-insensitive market_hash_name substring. | [optional] 

### Return type

[**AlertListResponse**](AlertListResponse.md)

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

# **update_alert**
> AlertDefinition update_alert(alert_id, alert_update_request)

Update Alert

Update threshold fields or enabled state for an existing alert.

At least one of `threshold_value`, `threshold_currency`, or `is_enabled` must be provided. Enabling an alert re-applies tier, configured-delivery-channel, and enabled-alert-limit checks.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.alert_definition import AlertDefinition
from cs2cap.models.alert_update_request import AlertUpdateRequest
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
    api_instance = cs2cap.AccountAlertsApi(api_client)
    alert_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | 
    alert_update_request = cs2cap.AlertUpdateRequest() # AlertUpdateRequest | 

    try:
        # Update Alert
        api_response = api_instance.update_alert(alert_id, alert_update_request)
        print("The response of AccountAlertsApi->update_alert:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAlertsApi->update_alert: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **alert_id** | **UUID**|  | 
 **alert_update_request** | [**AlertUpdateRequest**](AlertUpdateRequest.md)|  | 

### Return type

[**AlertDefinition**](AlertDefinition.md)

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

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

