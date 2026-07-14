# MarketItemsSnapshotItem

Summary-only item row for /v1/market/items.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**summary** | [**MarketItemAnalyticsSummary**](MarketItemAnalyticsSummary.md) | Summary value. | 

## Example

```python
from cs2cap.models.market_items_snapshot_item import MarketItemsSnapshotItem

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemsSnapshotItem from a JSON string
market_items_snapshot_item_instance = MarketItemsSnapshotItem.from_json(json)
# print the JSON string representation of the object
print(MarketItemsSnapshotItem.to_json())

# convert the object into a dict
market_items_snapshot_item_dict = market_items_snapshot_item_instance.to_dict()
# create an instance of MarketItemsSnapshotItem from a dict
market_items_snapshot_item_from_dict = MarketItemsSnapshotItem.from_dict(market_items_snapshot_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


