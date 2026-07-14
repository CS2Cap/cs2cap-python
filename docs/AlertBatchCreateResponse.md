# AlertBatchCreateResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**created** | **int** | Number of alerts created successfully. | 
**failed** | **int** | Number of batch items that failed inline validation. | 
**results** | [**List[AlertBatchCreateResult]**](AlertBatchCreateResult.md) | Ordered per-item outcomes matching the request payload order. | 

## Example

```python
from cs2cap.models.alert_batch_create_response import AlertBatchCreateResponse

# TODO update the JSON string below
json = "{}"
# create an instance of AlertBatchCreateResponse from a JSON string
alert_batch_create_response_instance = AlertBatchCreateResponse.from_json(json)
# print the JSON string representation of the object
print(AlertBatchCreateResponse.to_json())

# convert the object into a dict
alert_batch_create_response_dict = alert_batch_create_response_instance.to_dict()
# create an instance of AlertBatchCreateResponse from a dict
alert_batch_create_response_from_dict = AlertBatchCreateResponse.from_dict(alert_batch_create_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


