# MarketItemsSnapshotData

Payload for /v1/market/items.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**items** | [**List[MarketItemsSnapshotItem]**](MarketItemsSnapshotItem.md) | Returned market item summaries. | 

## Example

```python
from cs2cap.models.market_items_snapshot_data import MarketItemsSnapshotData

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemsSnapshotData from a JSON string
market_items_snapshot_data_instance = MarketItemsSnapshotData.from_json(json)
# print the JSON string representation of the object
print(MarketItemsSnapshotData.to_json())

# convert the object into a dict
market_items_snapshot_data_dict = market_items_snapshot_data_instance.to_dict()
# create an instance of MarketItemsSnapshotData from a dict
market_items_snapshot_data_from_dict = MarketItemsSnapshotData.from_dict(market_items_snapshot_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


