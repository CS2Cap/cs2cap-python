# cs2cap.ItemsApi

All URIs are relative to *https://api.cs2c.app*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_item_catalog_metadata**](ItemsApi.md#get_item_catalog_metadata) | **GET** /v1/items/metadata | Get Item Catalog Metadata
[**list_items**](ItemsApi.md#list_items) | **GET** /v1/items | List Items


# **get_item_catalog_metadata**
> ItemsMetadataResponse get_item_catalog_metadata()

Get Item Catalog Metadata

Return catalog counts and filter option values for frontend search controls.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.items_metadata_response import ItemsMetadataResponse
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
    api_instance = cs2cap.ItemsApi(api_client)

    try:
        # Get Item Catalog Metadata
        api_response = api_instance.get_item_catalog_metadata()
        print("The response of ItemsApi->get_item_catalog_metadata:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ItemsApi->get_item_catalog_metadata: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**ItemsMetadataResponse**](ItemsMetadataResponse.md)

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

# **list_items**
> ItemsPaginatedResponseItemOut list_items(q=q, item_id=item_id, market_hash_name=market_hash_name, item_type=item_type, item_subtype=item_subtype, weapon_type=weapon_type, base_name=base_name, skin_name=skin_name, wear_name=wear_name, phase=phase, collection=collection, crates=crates, rarity_name=rarity_name, rarity_color=rarity_color, style_name=style_name, is_stattrak=is_stattrak, is_souvenir=is_souvenir, limit=limit, offset=offset)

List Items

Search the normalized CS2 item catalog with exact-match metadata filters and simple result limiting.

Filters:
- exact catalog fields such as `item_type`, `collection`, `rarity_name`, and `phase`
- `q` for case-insensitive substring search on `market_hash_name`
- `item_id` for direct lookup

Result limiting:
- provide `limit` to cap the number of returned items (still tier-capped, endpoint max 1000)
- omit `limit` to return all matched items in one response, for any tier

Response:
- item records with canonical identifiers and item metadata
- optional `supply` values when available

Use this endpoint to resolve canonical `item_id` values before calling prices, bids, sales, or market analytics.

### Example

* Bearer Authentication (BearerAuth):

```python
import cs2cap
from cs2cap.models.items_paginated_response_item_out import ItemsPaginatedResponseItemOut
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
    api_instance = cs2cap.ItemsApi(api_client)
    q = 'q_example' # str | Search by name substring (case-insensitive) (optional)
    item_id = 56 # int | Exact item ID match (optional)
    market_hash_name = 'market_hash_name_example' # str | Exact market hash name match (case-insensitive) (optional)
    item_type = 'item_type_example' # str | Exact item type match (case-insensitive). Options: Weapon, Sticker, Sticker Slab, Graffiti, Charm, Crate, Music Kit, Patch, Collectible, Agent, Key, Tool. (optional)
    item_subtype = 'item_subtype_example' # str | Exact item subtype match (case-insensitive). Options depend on item_type (for example Equipment, Gloves, Rifles, Autograph, Team, Capsule Key). (optional)
    weapon_type = 'weapon_type_example' # str | Exact weapon type match (case-insensitive) (optional)
    base_name = 'base_name_example' # str | Exact base name match (case-insensitive) (optional)
    skin_name = 'skin_name_example' # str | Exact skin name match (case-insensitive) (optional)
    wear_name = 'wear_name_example' # str | Exact wear name match (case-insensitive) (optional)
    phase = 'phase_example' # str | Exact phase match (case-insensitive) (optional)
    collection = 'collection_example' # str | Exact collection match (case-insensitive) (optional)
    crates = ['crates_example'] # List[str] | Filter by crate names (matches any provided value) (optional)
    rarity_name = 'rarity_name_example' # str | Exact rarity name match (case-insensitive) (optional)
    rarity_color = 'rarity_color_example' # str | Exact rarity color match (case-insensitive) (optional)
    style_name = 'style_name_example' # str | Exact style name match (case-insensitive) (optional)
    is_stattrak = True # bool | Filter by StatTrak items (optional)
    is_souvenir = True # bool | Filter by Souvenir items (optional)
    limit = 56 # int | Maximum number of items to return. Omit to return all matched items in one response. (optional)
    offset = 56 # int | Number of items to skip before returning results. (optional)

    try:
        # List Items
        api_response = api_instance.list_items(q=q, item_id=item_id, market_hash_name=market_hash_name, item_type=item_type, item_subtype=item_subtype, weapon_type=weapon_type, base_name=base_name, skin_name=skin_name, wear_name=wear_name, phase=phase, collection=collection, crates=crates, rarity_name=rarity_name, rarity_color=rarity_color, style_name=style_name, is_stattrak=is_stattrak, is_souvenir=is_souvenir, limit=limit, offset=offset)
        print("The response of ItemsApi->list_items:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling ItemsApi->list_items: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **q** | **str**| Search by name substring (case-insensitive) | [optional] 
 **item_id** | **int**| Exact item ID match | [optional] 
 **market_hash_name** | **str**| Exact market hash name match (case-insensitive) | [optional] 
 **item_type** | **str**| Exact item type match (case-insensitive). Options: Weapon, Sticker, Sticker Slab, Graffiti, Charm, Crate, Music Kit, Patch, Collectible, Agent, Key, Tool. | [optional] 
 **item_subtype** | **str**| Exact item subtype match (case-insensitive). Options depend on item_type (for example Equipment, Gloves, Rifles, Autograph, Team, Capsule Key). | [optional] 
 **weapon_type** | **str**| Exact weapon type match (case-insensitive) | [optional] 
 **base_name** | **str**| Exact base name match (case-insensitive) | [optional] 
 **skin_name** | **str**| Exact skin name match (case-insensitive) | [optional] 
 **wear_name** | **str**| Exact wear name match (case-insensitive) | [optional] 
 **phase** | **str**| Exact phase match (case-insensitive) | [optional] 
 **collection** | **str**| Exact collection match (case-insensitive) | [optional] 
 **crates** | [**List[str]**](str.md)| Filter by crate names (matches any provided value) | [optional] 
 **rarity_name** | **str**| Exact rarity name match (case-insensitive) | [optional] 
 **rarity_color** | **str**| Exact rarity color match (case-insensitive) | [optional] 
 **style_name** | **str**| Exact style name match (case-insensitive) | [optional] 
 **is_stattrak** | **bool**| Filter by StatTrak items | [optional] 
 **is_souvenir** | **bool**| Filter by Souvenir items | [optional] 
 **limit** | **int**| Maximum number of items to return. Omit to return all matched items in one response. | [optional] 
 **offset** | **int**| Number of items to skip before returning results. | [optional] 

### Return type

[**ItemsPaginatedResponseItemOut**](ItemsPaginatedResponseItemOut.md)

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

