# PortfolioLineItem

Valuation line item for one portfolio entry.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**quantity** | **int** | Number of units held. | 
**best_ask** | **int** |  | [optional] 
**best_bid** | **int** |  | [optional] 
**item_value** | **int** |  | [optional] 
**image_url** | **str** |  | [optional] 
**rarity_name** | **str** |  | [optional] 
**rarity_color** | **str** |  | [optional] 
**providers** | [**List[BatchPriceQuote]**](BatchPriceQuote.md) | Per-provider price quotes. | [optional] 

## Example

```python
from cs2cap.models.portfolio_line_item import PortfolioLineItem

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioLineItem from a JSON string
portfolio_line_item_instance = PortfolioLineItem.from_json(json)
# print the JSON string representation of the object
print(PortfolioLineItem.to_json())

# convert the object into a dict
portfolio_line_item_dict = portfolio_line_item_instance.to_dict()
# create an instance of PortfolioLineItem from a dict
portfolio_line_item_from_dict = PortfolioLineItem.from_dict(portfolio_line_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


