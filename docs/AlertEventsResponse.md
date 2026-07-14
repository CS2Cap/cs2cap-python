# AlertEventsResponse

Paginated alert event history.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**events** | [**List[AlertEventSummary]**](AlertEventSummary.md) | Recent alert trigger events. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Pagination metadata. | 

## Example

```python
from cs2cap.models.alert_events_response import AlertEventsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of AlertEventsResponse from a JSON string
alert_events_response_instance = AlertEventsResponse.from_json(json)
# print the JSON string representation of the object
print(AlertEventsResponse.to_json())

# convert the object into a dict
alert_events_response_dict = alert_events_response_instance.to_dict()
# create an instance of AlertEventsResponse from a dict
alert_events_response_from_dict = AlertEventsResponse.from_dict(alert_events_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


