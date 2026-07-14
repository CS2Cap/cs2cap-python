# AlertListResponse

Paginated response for configured alerts.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**alerts** | [**List[AlertDefinition]**](AlertDefinition.md) | Configured alert rules. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Pagination metadata. | 

## Example

```python
from cs2cap.models.alert_list_response import AlertListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of AlertListResponse from a JSON string
alert_list_response_instance = AlertListResponse.from_json(json)
# print the JSON string representation of the object
print(AlertListResponse.to_json())

# convert the object into a dict
alert_list_response_dict = alert_list_response_instance.to_dict()
# create an instance of AlertListResponse from a dict
alert_list_response_from_dict = AlertListResponse.from_dict(alert_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


