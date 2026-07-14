# cs2cap.AccountAPIKeysApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_sub_key**](AccountAPIKeysApi.md#create_sub_key) | **POST** /v1/account/sub-keys | Create Sub Key
[**delete_sub_key**](AccountAPIKeysApi.md#delete_sub_key) | **DELETE** /v1/account/sub-keys/{key_id} | Delete Sub Key
[**get_sub_key**](AccountAPIKeysApi.md#get_sub_key) | **GET** /v1/account/sub-keys/{key_id} | Get Sub Key
[**list_sub_keys**](AccountAPIKeysApi.md#list_sub_keys) | **GET** /v1/account/sub-keys | List Sub Keys
[**reissue_sub_key**](AccountAPIKeysApi.md#reissue_sub_key) | **POST** /v1/account/sub-keys/{key_id}/reissue | Reissue Sub Key
[**update_sub_key**](AccountAPIKeysApi.md#update_sub_key) | **PATCH** /v1/account/sub-keys/{key_id} | Update Sub Key


# **create_sub_key**
> ChildAPIKeyCreateResponse create_sub_key(child_api_key_create_request)

Create Sub Key

Create one child API key under the active root key.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.child_api_key_create_request import ChildAPIKeyCreateRequest
from cs2cap.models.child_api_key_create_response import ChildAPIKeyCreateResponse
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
    api_instance = cs2cap.AccountAPIKeysApi(api_client)
    child_api_key_create_request = cs2cap.ChildAPIKeyCreateRequest() # ChildAPIKeyCreateRequest | 

    try:
        # Create Sub Key
        api_response = api_instance.create_sub_key(child_api_key_create_request)
        print("The response of AccountAPIKeysApi->create_sub_key:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAPIKeysApi->create_sub_key: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **child_api_key_create_request** | [**ChildAPIKeyCreateRequest**](ChildAPIKeyCreateRequest.md)|  | 

### Return type

[**ChildAPIKeyCreateResponse**](ChildAPIKeyCreateResponse.md)

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

# **delete_sub_key**
> Dict[str, object] delete_sub_key(key_id)

Delete Sub Key

Revoke one active child API key.

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
    api_instance = cs2cap.AccountAPIKeysApi(api_client)
    key_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | Child API key ID.

    try:
        # Delete Sub Key
        api_response = api_instance.delete_sub_key(key_id)
        print("The response of AccountAPIKeysApi->delete_sub_key:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAPIKeysApi->delete_sub_key: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key_id** | **UUID**| Child API key ID. | 

### Return type

**Dict[str, object]**

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

# **get_sub_key**
> ChildAPIKeyDetailResponse get_sub_key(key_id)

Get Sub Key

Get one active child API key.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.child_api_key_detail_response import ChildAPIKeyDetailResponse
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
    api_instance = cs2cap.AccountAPIKeysApi(api_client)
    key_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | Child API key ID.

    try:
        # Get Sub Key
        api_response = api_instance.get_sub_key(key_id)
        print("The response of AccountAPIKeysApi->get_sub_key:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAPIKeysApi->get_sub_key: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key_id** | **UUID**| Child API key ID. | 

### Return type

[**ChildAPIKeyDetailResponse**](ChildAPIKeyDetailResponse.md)

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

# **list_sub_keys**
> ChildAPIKeyListResponse list_sub_keys(limit=limit, offset=offset)

List Sub Keys

List active child API keys.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.child_api_key_list_response import ChildAPIKeyListResponse
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
    api_instance = cs2cap.AccountAPIKeysApi(api_client)
    limit = 25 # int | Requested page size. Values are clamped to the range 1..100. (optional) (default to 25)
    offset = 0 # int | Zero-based starting position for this page. (optional) (default to 0)

    try:
        # List Sub Keys
        api_response = api_instance.list_sub_keys(limit=limit, offset=offset)
        print("The response of AccountAPIKeysApi->list_sub_keys:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAPIKeysApi->list_sub_keys: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **limit** | **int**| Requested page size. Values are clamped to the range 1..100. | [optional] [default to 25]
 **offset** | **int**| Zero-based starting position for this page. | [optional] [default to 0]

### Return type

[**ChildAPIKeyListResponse**](ChildAPIKeyListResponse.md)

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

# **reissue_sub_key**
> ChildAPIKeyCreateResponse reissue_sub_key(key_id)

Reissue Sub Key

Rotate one active child API key.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.child_api_key_create_response import ChildAPIKeyCreateResponse
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
    api_instance = cs2cap.AccountAPIKeysApi(api_client)
    key_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | Child API key ID.

    try:
        # Reissue Sub Key
        api_response = api_instance.reissue_sub_key(key_id)
        print("The response of AccountAPIKeysApi->reissue_sub_key:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAPIKeysApi->reissue_sub_key: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key_id** | **UUID**| Child API key ID. | 

### Return type

[**ChildAPIKeyCreateResponse**](ChildAPIKeyCreateResponse.md)

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

# **update_sub_key**
> ChildAPIKeyDetailResponse update_sub_key(key_id, child_api_key_update_request)

Update Sub Key

Update one active child API key.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.child_api_key_detail_response import ChildAPIKeyDetailResponse
from cs2cap.models.child_api_key_update_request import ChildAPIKeyUpdateRequest
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
    api_instance = cs2cap.AccountAPIKeysApi(api_client)
    key_id = UUID('38400000-8cf0-11bd-b23e-10b96e4ef00d') # UUID | Child API key ID.
    child_api_key_update_request = cs2cap.ChildAPIKeyUpdateRequest() # ChildAPIKeyUpdateRequest | 

    try:
        # Update Sub Key
        api_response = api_instance.update_sub_key(key_id, child_api_key_update_request)
        print("The response of AccountAPIKeysApi->update_sub_key:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountAPIKeysApi->update_sub_key: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **key_id** | **UUID**| Child API key ID. | 
 **child_api_key_update_request** | [**ChildAPIKeyUpdateRequest**](ChildAPIKeyUpdateRequest.md)|  | 

### Return type

[**ChildAPIKeyDetailResponse**](ChildAPIKeyDetailResponse.md)

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

