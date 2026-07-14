# WatchlistCreateSingleRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID to save to the watchlist. | 

## Example

```python
from cs2cap.models.watchlist_create_single_request import WatchlistCreateSingleRequest

# TODO update the JSON string below
json = "{}"
# create an instance of WatchlistCreateSingleRequest from a JSON string
watchlist_create_single_request_instance = WatchlistCreateSingleRequest.from_json(json)
# print the JSON string representation of the object
print(WatchlistCreateSingleRequest.to_json())

# convert the object into a dict
watchlist_create_single_request_dict = watchlist_create_single_request_instance.to_dict()
# create an instance of WatchlistCreateSingleRequest from a dict
watchlist_create_single_request_from_dict = WatchlistCreateSingleRequest.from_dict(watchlist_create_single_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


