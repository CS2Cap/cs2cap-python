# AlertDefinition

Configured alert rule.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique alert identifier. | 
**kind** | **str** | Alert kind. | 
**threshold_value** | **str** | Threshold value in configured units. | 
**threshold_currency** | **str** |  | [optional] 
**is_enabled** | **bool** | Whether the alert is enabled. | 
**last_triggered_at** | **datetime** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when the alert was created. | 
**updated_at** | **datetime** | ISO 8601 UTC timestamp when the alert was last updated. | 
**item** | [**AlertItemSummary**](AlertItemSummary.md) | Item metadata for the alert target. | 

## Example

```python
from cs2cap.models.alert_definition import AlertDefinition

# TODO update the JSON string below
json = "{}"
# create an instance of AlertDefinition from a JSON string
alert_definition_instance = AlertDefinition.from_json(json)
# print the JSON string representation of the object
print(AlertDefinition.to_json())

# convert the object into a dict
alert_definition_dict = alert_definition_instance.to_dict()
# create an instance of AlertDefinition from a dict
alert_definition_from_dict = AlertDefinition.from_dict(alert_definition_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


