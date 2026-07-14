# AlertBatchCreateRequest


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**alerts** | [**List[AlertCreateRequest]**](AlertCreateRequest.md) | Alert definitions to create in a single request. | 

## Example

```python
from cs2cap.models.alert_batch_create_request import AlertBatchCreateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of AlertBatchCreateRequest from a JSON string
alert_batch_create_request_instance = AlertBatchCreateRequest.from_json(json)
# print the JSON string representation of the object
print(AlertBatchCreateRequest.to_json())

# convert the object into a dict
alert_batch_create_request_dict = alert_batch_create_request_instance.to_dict()
# create an instance of AlertBatchCreateRequest from a dict
alert_batch_create_request_from_dict = AlertBatchCreateRequest.from_dict(alert_batch_create_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


