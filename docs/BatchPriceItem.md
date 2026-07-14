# BatchPriceItem

Aggregated price data for one item across providers.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**quotes** | [**List[BatchPriceQuote]**](BatchPriceQuote.md) | Per-provider price quotes. | 

## Example

```python
from cs2cap.models.batch_price_item import BatchPriceItem

# TODO update the JSON string below
json = "{}"
# create an instance of BatchPriceItem from a JSON string
batch_price_item_instance = BatchPriceItem.from_json(json)
# print the JSON string representation of the object
print(BatchPriceItem.to_json())

# convert the object into a dict
batch_price_item_dict = batch_price_item_instance.to_dict()
# create an instance of BatchPriceItem from a dict
batch_price_item_from_dict = BatchPriceItem.from_dict(batch_price_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


