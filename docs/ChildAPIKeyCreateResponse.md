# ChildAPIKeyCreateResponse

Plaintext child-key creation response.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **str** | API key value. This is typically shown only once. | 
**key_info** | [**APIKeyInfo**](APIKeyInfo.md) | Metadata for the created child API key. | 
**message** | **str** | Human-readable status message. | [optional] [default to 'Store this key securely. It will not be shown again.']

## Example

```python
from cs2cap.models.child_api_key_create_response import ChildAPIKeyCreateResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ChildAPIKeyCreateResponse from a JSON string
child_api_key_create_response_instance = ChildAPIKeyCreateResponse.from_json(json)
# print the JSON string representation of the object
print(ChildAPIKeyCreateResponse.to_json())

# convert the object into a dict
child_api_key_create_response_dict = child_api_key_create_response_instance.to_dict()
# create an instance of ChildAPIKeyCreateResponse from a dict
child_api_key_create_response_from_dict = ChildAPIKeyCreateResponse.from_dict(child_api_key_create_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


