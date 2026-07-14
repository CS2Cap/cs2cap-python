# ChildAPIKeyDetailResponse

One child key plus current-month usage summary.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | [**APIKeyInfo**](APIKeyInfo.md) | Child API key metadata. | 
**requests_this_month** | **int** | Current-month request count for this child key. | 

## Example

```python
from cs2cap.models.child_api_key_detail_response import ChildAPIKeyDetailResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ChildAPIKeyDetailResponse from a JSON string
child_api_key_detail_response_instance = ChildAPIKeyDetailResponse.from_json(json)
# print the JSON string representation of the object
print(ChildAPIKeyDetailResponse.to_json())

# convert the object into a dict
child_api_key_detail_response_dict = child_api_key_detail_response_instance.to_dict()
# create an instance of ChildAPIKeyDetailResponse from a dict
child_api_key_detail_response_from_dict = ChildAPIKeyDetailResponse.from_dict(child_api_key_detail_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


