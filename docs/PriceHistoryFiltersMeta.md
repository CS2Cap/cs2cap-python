# PriceHistoryFiltersMeta

Filter metadata for price history endpoint.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** |  | [optional] 
**market_hash_name** | **str** |  | [optional] 
**phase** | **str** |  | [optional] 
**provider** | [**AllProviders**](AllProviders.md) |  | [optional] 
**start** | **datetime** |  | [optional] 
**end** | **datetime** |  | [optional] 

## Example

```python
from cs2cap.models.price_history_filters_meta import PriceHistoryFiltersMeta

# TODO update the JSON string below
json = "{}"
# create an instance of PriceHistoryFiltersMeta from a JSON string
price_history_filters_meta_instance = PriceHistoryFiltersMeta.from_json(json)
# print the JSON string representation of the object
print(PriceHistoryFiltersMeta.to_json())

# convert the object into a dict
price_history_filters_meta_dict = price_history_filters_meta_instance.to_dict()
# create an instance of PriceHistoryFiltersMeta from a dict
price_history_filters_meta_from_dict = PriceHistoryFiltersMeta.from_dict(price_history_filters_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


