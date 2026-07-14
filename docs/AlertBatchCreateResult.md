# AlertBatchCreateResult


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**index** | **int** | Zero-based index of the original request item. | 
**status** | **str** | Per-item processing status. | 
**alert_id** | **str** |  | [optional] 
**code** | **str** |  | [optional] 
**message** | **str** |  | [optional] 

## Example

```python
from cs2cap.models.alert_batch_create_result import AlertBatchCreateResult

# TODO update the JSON string below
json = "{}"
# create an instance of AlertBatchCreateResult from a JSON string
alert_batch_create_result_instance = AlertBatchCreateResult.from_json(json)
# print the JSON string representation of the object
print(AlertBatchCreateResult.to_json())

# convert the object into a dict
alert_batch_create_result_dict = alert_batch_create_result_instance.to_dict()
# create an instance of AlertBatchCreateResult from a dict
alert_batch_create_result_from_dict = AlertBatchCreateResult.from_dict(alert_batch_create_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


