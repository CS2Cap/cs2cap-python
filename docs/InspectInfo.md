# InspectInfo

In-game inspect link and screenshot URLs.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**in_game** | **str** |  | [optional] 
**screenshot_front** | **str** |  | [optional] 
**screenshot_back** | **str** |  | [optional] 

## Example

```python
from cs2cap.models.inspect_info import InspectInfo

# TODO update the JSON string below
json = "{}"
# create an instance of InspectInfo from a JSON string
inspect_info_instance = InspectInfo.from_json(json)
# print the JSON string representation of the object
print(InspectInfo.to_json())

# convert the object into a dict
inspect_info_dict = inspect_info_instance.to_dict()
# create an instance of InspectInfo from a dict
inspect_info_from_dict = InspectInfo.from_dict(inspect_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


