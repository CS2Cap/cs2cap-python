# StickerInfo

Sticker information.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Display name for this entity. | 
**slot** | **int** | Sticker slot index on the item. | 
**wear** | **float** |  | [optional] 

## Example

```python
from cs2cap.models.sticker_info import StickerInfo

# TODO update the JSON string below
json = "{}"
# create an instance of StickerInfo from a JSON string
sticker_info_instance = StickerInfo.from_json(json)
# print the JSON string representation of the object
print(StickerInfo.to_json())

# convert the object into a dict
sticker_info_dict = sticker_info_instance.to_dict()
# create an instance of StickerInfo from a dict
sticker_info_from_dict = StickerInfo.from_dict(sticker_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


