# WatchlistCreateResponse

Response body for POST /v1/account/watchlist.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique identifier for this saved entry. | 
**item_id** | **int** | Normalized catalog item ID. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when this entry was created. | 
**items** | [**List[WatchlistItem]**](WatchlistItem.md) | Watchlist entries created by this request. | 
**created_count** | **int** | Number of watchlist entries created. | 

## Example

```python
from cs2cap.models.watchlist_create_response import WatchlistCreateResponse

# TODO update the JSON string below
json = "{}"
# create an instance of WatchlistCreateResponse from a JSON string
watchlist_create_response_instance = WatchlistCreateResponse.from_json(json)
# print the JSON string representation of the object
print(WatchlistCreateResponse.to_json())

# convert the object into a dict
watchlist_create_response_dict = watchlist_create_response_instance.to_dict()
# create an instance of WatchlistCreateResponse from a dict
watchlist_create_response_from_dict = WatchlistCreateResponse.from_dict(watchlist_create_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


