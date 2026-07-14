# MarketItem

An item's price data from a specific provider.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **str** | Provider key used by this API. | 
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**lowest_ask** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**lowest_ask_decimal** | **str** |  | [optional] 
**quantity** | **int** | Quantity count for this record. | 
**link** | **str** |  | [optional] 
**url** | **str** |  | [optional] 
**timestamp** | **datetime** |  | [optional] 
**last_updated** | **datetime** |  | [optional] 

## Example

```python
from cs2cap.models.market_item import MarketItem

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItem from a JSON string
market_item_instance = MarketItem.from_json(json)
# print the JSON string representation of the object
print(MarketItem.to_json())

# convert the object into a dict
market_item_dict = market_item_instance.to_dict()
# create an instance of MarketItem from a dict
market_item_from_dict = MarketItem.from_dict(market_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


