# BuyOrderItem

Buy order data for a specific item from a provider.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**provider** | **str** | Provider key used by this API. | 
**highest_bid** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**highest_bid_decimal** | **str** |  | [optional] 
**num_bids** | **int** | Num bids value. | 
**timestamp** | **datetime** |  | [optional] 
**last_updated** | **datetime** |  | [optional] 

## Example

```python
from cs2cap.models.buy_order_item import BuyOrderItem

# TODO update the JSON string below
json = "{}"
# create an instance of BuyOrderItem from a JSON string
buy_order_item_instance = BuyOrderItem.from_json(json)
# print the JSON string representation of the object
print(BuyOrderItem.to_json())

# convert the object into a dict
buy_order_item_dict = buy_order_item_instance.to_dict()
# create an instance of BuyOrderItem from a dict
buy_order_item_from_dict = BuyOrderItem.from_dict(buy_order_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


