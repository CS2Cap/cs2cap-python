# WatchlistCreateBatchRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_ids** | **List[int]** | Normalized catalog item IDs to save to the watchlist in one request. | 

## Example

```python
from cs2cap.models.watchlist_create_batch_request import WatchlistCreateBatchRequest

# TODO update the JSON string below
json = "{}"
# create an instance of WatchlistCreateBatchRequest from a JSON string
watchlist_create_batch_request_instance = WatchlistCreateBatchRequest.from_json(json)
# print the JSON string representation of the object
print(WatchlistCreateBatchRequest.to_json())

# convert the object into a dict
watchlist_create_batch_request_dict = watchlist_create_batch_request_instance.to_dict()
# create an instance of WatchlistCreateBatchRequest from a dict
watchlist_create_batch_request_from_dict = WatchlistCreateBatchRequest.from_dict(watchlist_create_batch_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


