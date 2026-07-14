# PriceCandlesMeta

Metadata for candles response (constant across all items).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**provider** | **str** | Composite provider scope for this response. | [optional] [default to 'All Providers']
**currency** | **str** | ISO 4217 currency code for the value context. | 
**interval** | **str** | Time bucket interval used for aggregation. | 
**start** | **datetime** | Inclusive start timestamp for the requested window (UTC). | 
**end** | **datetime** | Exclusive end timestamp for the requested window (UTC). | 

## Example

```python
from cs2cap.models.price_candles_meta import PriceCandlesMeta

# TODO update the JSON string below
json = "{}"
# create an instance of PriceCandlesMeta from a JSON string
price_candles_meta_instance = PriceCandlesMeta.from_json(json)
# print the JSON string representation of the object
print(PriceCandlesMeta.to_json())

# convert the object into a dict
price_candles_meta_dict = price_candles_meta_instance.to_dict()
# create an instance of PriceCandlesMeta from a dict
price_candles_meta_from_dict = PriceCandlesMeta.from_dict(price_candles_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


