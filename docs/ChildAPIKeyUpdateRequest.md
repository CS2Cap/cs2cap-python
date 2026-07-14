# ChildAPIKeyUpdateRequest

Update mutable child-key fields.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | [optional] 
**quota_requests_per_month_override** | **int** |  | [optional] 
**rate_requests_per_minute_override** | **int** |  | [optional] 

## Example

```python
from cs2cap.models.child_api_key_update_request import ChildAPIKeyUpdateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of ChildAPIKeyUpdateRequest from a JSON string
child_api_key_update_request_instance = ChildAPIKeyUpdateRequest.from_json(json)
# print the JSON string representation of the object
print(ChildAPIKeyUpdateRequest.to_json())

# convert the object into a dict
child_api_key_update_request_dict = child_api_key_update_request_instance.to_dict()
# create an instance of ChildAPIKeyUpdateRequest from a dict
child_api_key_update_request_from_dict = ChildAPIKeyUpdateRequest.from_dict(child_api_key_update_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


