# WatchlistItem

One saved watchlist entry.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique identifier for this saved entry. | 
**item_id** | **int** | Normalized catalog item ID. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when this entry was created. | 

## Example

```python
from cs2cap.models.watchlist_item import WatchlistItem

# TODO update the JSON string below
json = "{}"
# create an instance of WatchlistItem from a JSON string
watchlist_item_instance = WatchlistItem.from_json(json)
# print the JSON string representation of the object
print(WatchlistItem.to_json())

# convert the object into a dict
watchlist_item_dict = watchlist_item_instance.to_dict()
# create an instance of WatchlistItem from a dict
watchlist_item_from_dict = WatchlistItem.from_dict(watchlist_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


