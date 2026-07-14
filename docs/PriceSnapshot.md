# PriceSnapshot

Single price snapshot at a point in time.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**provider** | **str** | Provider key used by this API. | 
**time** | **datetime** | Time value. | 
**price** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**currency** | **str** | ISO 4217 currency code for the value context. | 
**quantity** | **int** | Quantity value. | 

## Example

```python
from cs2cap.models.price_snapshot import PriceSnapshot

# TODO update the JSON string below
json = "{}"
# create an instance of PriceSnapshot from a JSON string
price_snapshot_instance = PriceSnapshot.from_json(json)
# print the JSON string representation of the object
print(PriceSnapshot.to_json())

# convert the object into a dict
price_snapshot_dict = price_snapshot_instance.to_dict()
# create an instance of PriceSnapshot from a dict
price_snapshot_from_dict = PriceSnapshot.from_dict(price_snapshot_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


