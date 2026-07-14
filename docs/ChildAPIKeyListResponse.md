# ChildAPIKeyListResponse

Paginated child-key listing.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**keys** | [**List[ChildAPIKeyDetailResponse]**](ChildAPIKeyDetailResponse.md) | Child API keys. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Offset pagination metadata. | 

## Example

```python
from cs2cap.models.child_api_key_list_response import ChildAPIKeyListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ChildAPIKeyListResponse from a JSON string
child_api_key_list_response_instance = ChildAPIKeyListResponse.from_json(json)
# print the JSON string representation of the object
print(ChildAPIKeyListResponse.to_json())

# convert the object into a dict
child_api_key_list_response_dict = child_api_key_list_response_instance.to_dict()
# create an instance of ChildAPIKeyListResponse from a dict
child_api_key_list_response_from_dict = ChildAPIKeyListResponse.from_dict(child_api_key_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


