# CharmInfo

Charm/keychain information.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Display name for this entity. | 
**pattern_id** | **int** |  | [optional] 

## Example

```python
from cs2cap.models.charm_info import CharmInfo

# TODO update the JSON string below
json = "{}"
# create an instance of CharmInfo from a JSON string
charm_info_instance = CharmInfo.from_json(json)
# print the JSON string representation of the object
print(CharmInfo.to_json())

# convert the object into a dict
charm_info_dict = charm_info_instance.to_dict()
# create an instance of CharmInfo from a dict
charm_info_from_dict = CharmInfo.from_dict(charm_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


