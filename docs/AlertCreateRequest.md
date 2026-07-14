# AlertCreateRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID to monitor. | 
**kind** | **str** | Alert kind: price_below, price_above, or spread_exceeds. | 
**threshold_value** | **str** | Threshold value in alert units. | 
**threshold_currency** | **str** |  | [optional] 
**is_enabled** | **bool** | Whether the alert should be enabled immediately. | [optional] [default to True]

## Example

```python
from cs2cap.models.alert_create_request import AlertCreateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of AlertCreateRequest from a JSON string
alert_create_request_instance = AlertCreateRequest.from_json(json)
# print the JSON string representation of the object
print(AlertCreateRequest.to_json())

# convert the object into a dict
alert_create_request_dict = alert_create_request_instance.to_dict()
# create an instance of AlertCreateRequest from a dict
alert_create_request_from_dict = AlertCreateRequest.from_dict(alert_create_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


