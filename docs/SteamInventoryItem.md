# SteamInventoryItem

A single item from a Steam CS2 inventory.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**assetid** | **str** | Steam asset ID — unique per inventory slot. | 
**market_hash_name** | **str** | Steam market hash name. | 
**phase** | **str** |  | [optional] 
**name** | **str** | Display name. | 
**icon_url** | **str** |  | [optional] 
**tradable** | **bool** | Whether the item is currently tradable. | 
**marketable** | **bool** | Whether the item can be listed on the Steam Market. | 
**quantity** | **int** | Stack size (almost always 1 for CS2 items). | 
**float_value** | **float** |  | [optional] 
**paint_seed** | **int** |  | [optional] 
**inspect_link** | **str** |  | [optional] 
**name_tag** | **str** |  | [optional] 
**stickers** | [**List[StickerInfo]**](StickerInfo.md) |  | [optional] 
**charms** | [**List[CharmInfo]**](CharmInfo.md) |  | [optional] 

## Example

```python
from cs2cap.models.steam_inventory_item import SteamInventoryItem

# TODO update the JSON string below
json = "{}"
# create an instance of SteamInventoryItem from a JSON string
steam_inventory_item_instance = SteamInventoryItem.from_json(json)
# print the JSON string representation of the object
print(SteamInventoryItem.to_json())

# convert the object into a dict
steam_inventory_item_dict = steam_inventory_item_instance.to_dict()
# create an instance of SteamInventoryItem from a dict
steam_inventory_item_from_dict = SteamInventoryItem.from_dict(steam_inventory_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


