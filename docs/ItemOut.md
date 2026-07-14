# ItemOut

Catalog item metadata returned by `/v1/items`.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** |  | [optional] 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**item_type** | **str** |  | [optional] 
**item_subtype** | **str** |  | [optional] 
**weapon_type** | **str** |  | [optional] 
**base_name** | **str** |  | [optional] 
**skin_name** | **str** |  | [optional] 
**wear_name** | **str** |  | [optional] 
**def_index** | **str** |  | [optional] 
**paint_index** | **int** |  | [optional] 
**collection** | **str** |  | [optional] 
**collection_image** | **str** |  | [optional] 
**crates** | **List[str]** |  | [optional] 
**crates_images** | **List[str]** |  | [optional] 
**release_date** | **date** |  | [optional] 
**rarity_name** | **str** |  | [optional] 
**rarity_color** | **str** |  | [optional] 
**style_name** | **str** |  | [optional] 
**is_stattrak** | **bool** |  | [optional] 
**is_souvenir** | **bool** |  | [optional] 
**min_float** | **float** |  | [optional] 
**max_float** | **float** |  | [optional] 
**image_url** | **str** |  | [optional] 
**supply** | **int** |  | [optional] 

## Example

```python
from cs2cap.models.item_out import ItemOut

# TODO update the JSON string below
json = "{}"
# create an instance of ItemOut from a JSON string
item_out_instance = ItemOut.from_json(json)
# print the JSON string representation of the object
print(ItemOut.to_json())

# convert the object into a dict
item_out_dict = item_out_instance.to_dict()
# create an instance of ItemOut from a dict
item_out_from_dict = ItemOut.from_dict(item_out_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


