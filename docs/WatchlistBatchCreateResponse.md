# WatchlistBatchCreateResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**items** | [**List[WatchlistItem]**](WatchlistItem.md) | Watchlist entries created by this request. | 
**created_count** | **int** | Number of watchlist entries created. | 

## Example

```python
from cs2cap.models.watchlist_batch_create_response import WatchlistBatchCreateResponse

# TODO update the JSON string below
json = "{}"
# create an instance of WatchlistBatchCreateResponse from a JSON string
watchlist_batch_create_response_instance = WatchlistBatchCreateResponse.from_json(json)
# print the JSON string representation of the object
print(WatchlistBatchCreateResponse.to_json())

# convert the object into a dict
watchlist_batch_create_response_dict = watchlist_batch_create_response_instance.to_dict()
# create an instance of WatchlistBatchCreateResponse from a dict
watchlist_batch_create_response_from_dict = WatchlistBatchCreateResponse.from_dict(watchlist_batch_create_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


