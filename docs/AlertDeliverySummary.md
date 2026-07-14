# AlertDeliverySummary

Outbound delivery result for one alert event.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**channel** | **str** | Delivery channel key. | 
**status** | **str** | Delivery status. | 
**delivery_id** | **str** |  | [optional] 
**endpoint_id** | **str** |  | [optional] 
**endpoint_label** | **str** |  | [optional] 
**platform** | **str** |  | [optional] 
**attempt_count** | **int** |  | [optional] 
**last_http_status** | **int** |  | [optional] 
**next_attempt_at** | **datetime** |  | [optional] 
**error** | **str** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when this delivery row was created. | 

## Example

```python
from cs2cap.models.alert_delivery_summary import AlertDeliverySummary

# TODO update the JSON string below
json = "{}"
# create an instance of AlertDeliverySummary from a JSON string
alert_delivery_summary_instance = AlertDeliverySummary.from_json(json)
# print the JSON string representation of the object
print(AlertDeliverySummary.to_json())

# convert the object into a dict
alert_delivery_summary_dict = alert_delivery_summary_instance.to_dict()
# create an instance of AlertDeliverySummary from a dict
alert_delivery_summary_from_dict = AlertDeliverySummary.from_dict(alert_delivery_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


