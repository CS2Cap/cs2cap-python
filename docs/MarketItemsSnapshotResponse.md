# MarketItemsSnapshotResponse

Response envelope for /v1/market/items.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**MarketMeta**](MarketMeta.md) | Response metadata for this payload. | 
**data** | [**MarketItemsSnapshotData**](MarketItemsSnapshotData.md) | Primary data payload for this response. | 

## Example

```python
from cs2cap.models.market_items_snapshot_response import MarketItemsSnapshotResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemsSnapshotResponse from a JSON string
market_items_snapshot_response_instance = MarketItemsSnapshotResponse.from_json(json)
# print the JSON string representation of the object
print(MarketItemsSnapshotResponse.to_json())

# convert the object into a dict
market_items_snapshot_response_dict = market_items_snapshot_response_instance.to_dict()
# create an instance of MarketItemsSnapshotResponse from a dict
market_items_snapshot_response_from_dict = MarketItemsSnapshotResponse.from_dict(market_items_snapshot_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


