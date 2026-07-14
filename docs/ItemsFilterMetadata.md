# ItemsFilterMetadata


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_type** | **List[str]** | Available item type filters. | 
**item_subtype** | **List[str]** | Available item subtype filters. | 
**weapon_type** | **List[str]** | Available weapon type filters. | 
**wear_name** | **List[str]** | Available wear filters. | 
**phase** | **List[str]** | Available phase filters. | 
**collection** | **List[str]** | Available collection filters. | 
**rarity_name** | **List[str]** | Available rarity-name filters. | 
**rarity_color** | **List[str]** | Available rarity-color filters. | 
**style_name** | **List[str]** | Available style-name filters. | 

## Example

```python
from cs2cap.models.items_filter_metadata import ItemsFilterMetadata

# TODO update the JSON string below
json = "{}"
# create an instance of ItemsFilterMetadata from a JSON string
items_filter_metadata_instance = ItemsFilterMetadata.from_json(json)
# print the JSON string representation of the object
print(ItemsFilterMetadata.to_json())

# convert the object into a dict
items_filter_metadata_dict = items_filter_metadata_instance.to_dict()
# create an instance of ItemsFilterMetadata from a dict
items_filter_metadata_from_dict = ItemsFilterMetadata.from_dict(items_filter_metadata_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


