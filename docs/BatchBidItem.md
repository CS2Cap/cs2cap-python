# BatchBidItem

Aggregated bid data for one item across providers.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**quotes** | [**List[BatchBidQuote]**](BatchBidQuote.md) | Per-provider bid quotes. | 

## Example

```python
from cs2cap.models.batch_bid_item import BatchBidItem

# TODO update the JSON string below
json = "{}"
# create an instance of BatchBidItem from a JSON string
batch_bid_item_instance = BatchBidItem.from_json(json)
# print the JSON string representation of the object
print(BatchBidItem.to_json())

# convert the object into a dict
batch_bid_item_dict = batch_bid_item_instance.to_dict()
# create an instance of BatchBidItem from a dict
batch_bid_item_from_dict = BatchBidItem.from_dict(batch_bid_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


