# AlertEventSummary

Recent alert trigger event.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique event identifier. | 
**alert_id** | **str** | Alert identifier that triggered. | 
**kind** | **str** | Alert kind. | 
**item** | [**AlertItemSummary**](AlertItemSummary.md) | Item metadata for the triggered alert. | 
**triggered_value** | **str** | Observed value that triggered the alert. | 
**triggered_currency** | **str** |  | [optional] 
**reason** | **str** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when the event was created. | 
**deliveries** | [**List[AlertDeliverySummary]**](AlertDeliverySummary.md) | Delivery attempts for this event. | 

## Example

```python
from cs2cap.models.alert_event_summary import AlertEventSummary

# TODO update the JSON string below
json = "{}"
# create an instance of AlertEventSummary from a JSON string
alert_event_summary_instance = AlertEventSummary.from_json(json)
# print the JSON string representation of the object
print(AlertEventSummary.to_json())

# convert the object into a dict
alert_event_summary_dict = alert_event_summary_instance.to_dict()
# create an instance of AlertEventSummary from a dict
alert_event_summary_from_dict = AlertEventSummary.from_dict(alert_event_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


