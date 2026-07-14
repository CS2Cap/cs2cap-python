# PriceHistoryMeta

Metadata for price history response.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | **str** | ISO 4217 currency code for the value context. | 
**filters** | [**PriceHistoryFiltersMeta**](PriceHistoryFiltersMeta.md) | Effective request filters applied to this response. | 
**result_count** | **int** | Number of records returned in this payload. | 

## Example

```python
from cs2cap.models.price_history_meta import PriceHistoryMeta

# TODO update the JSON string below
json = "{}"
# create an instance of PriceHistoryMeta from a JSON string
price_history_meta_instance = PriceHistoryMeta.from_json(json)
# print the JSON string representation of the object
print(PriceHistoryMeta.to_json())

# convert the object into a dict
price_history_meta_dict = price_history_meta_instance.to_dict()
# create an instance of PriceHistoryMeta from a dict
price_history_meta_from_dict = PriceHistoryMeta.from_dict(price_history_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


