# WatchlistResponse

Paginated watchlist response.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**items** | [**List[WatchlistItem]**](WatchlistItem.md) | Saved watchlist entries. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Pagination metadata. | 

## Example

```python
from cs2cap.models.watchlist_response import WatchlistResponse

# TODO update the JSON string below
json = "{}"
# create an instance of WatchlistResponse from a JSON string
watchlist_response_instance = WatchlistResponse.from_json(json)
# print the JSON string representation of the object
print(WatchlistResponse.to_json())

# convert the object into a dict
watchlist_response_dict = watchlist_response_instance.to_dict()
# create an instance of WatchlistResponse from a dict
watchlist_response_from_dict = WatchlistResponse.from_dict(watchlist_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


