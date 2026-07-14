# AlertUpdateRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**threshold_value** | **str** |  | [optional] 
**threshold_currency** | **str** |  | [optional] 
**is_enabled** | **bool** |  | [optional] 

## Example

```python
from cs2cap.models.alert_update_request import AlertUpdateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of AlertUpdateRequest from a JSON string
alert_update_request_instance = AlertUpdateRequest.from_json(json)
# print the JSON string representation of the object
print(AlertUpdateRequest.to_json())

# convert the object into a dict
alert_update_request_dict = alert_update_request_instance.to_dict()
# create an instance of AlertUpdateRequest from a dict
alert_update_request_from_dict = AlertUpdateRequest.from_dict(alert_update_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


