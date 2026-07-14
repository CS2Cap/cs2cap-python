# WatchlistCreateRequest

Request body for POST /v1/account/watchlist.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID to save to the watchlist. | 
**item_ids** | **List[int]** | Normalized catalog item IDs to save to the watchlist in one request. | 

## Example

```python
from cs2cap.models.watchlist_create_request import WatchlistCreateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of WatchlistCreateRequest from a JSON string
watchlist_create_request_instance = WatchlistCreateRequest.from_json(json)
# print the JSON string representation of the object
print(WatchlistCreateRequest.to_json())

# convert the object into a dict
watchlist_create_request_dict = watchlist_create_request_instance.to_dict()
# create an instance of WatchlistCreateRequest from a dict
watchlist_create_request_from_dict = WatchlistCreateRequest.from_dict(watchlist_create_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


