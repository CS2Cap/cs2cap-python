# PortfolioItemOut

A single item entry within a portfolio.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Entry UUID. | 
**item_id** | **int** | Catalog item ID. | 
**market_hash_name** | **str** | Steam market hash name. | 
**phase** | **str** |  | [optional] 
**quantity** | **int** | Number of units held. | 
**source** | **str** | How the item was added: &#39;steam&#39; or &#39;manual&#39;. | 
**steam_assetid** | **str** |  | [optional] 
**float_value** | **float** |  | [optional] 
**paint_seed** | **int** |  | [optional] 
**inspect_link** | **str** |  | [optional] 
**name_tag** | **str** |  | [optional] 
**stickers** | [**List[StickerInfo]**](StickerInfo.md) |  | [optional] 
**charms** | [**List[CharmInfo]**](CharmInfo.md) |  | [optional] 
**created_at** | **datetime** | When this entry was added. | 

## Example

```python
from cs2cap.models.portfolio_item_out import PortfolioItemOut

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioItemOut from a JSON string
portfolio_item_out_instance = PortfolioItemOut.from_json(json)
# print the JSON string representation of the object
print(PortfolioItemOut.to_json())

# convert the object into a dict
portfolio_item_out_dict = portfolio_item_out_instance.to_dict()
# create an instance of PortfolioItemOut from a dict
portfolio_item_out_from_dict = PortfolioItemOut.from_dict(portfolio_item_out_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


