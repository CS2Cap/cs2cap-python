# APIKeyInfo

Active API key information (without full key material).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique identifier for this resource. | 
**key_prefix** | **str** | Non-sensitive API key prefix used for identification. | 
**name** | **str** |  | [optional] 
**root_key_id** | **str** |  | [optional] 
**is_root_key** | **bool** | Whether this API key is a root key. | [optional] [default to True]
**is_active** | **bool** | Whether this resource is active. | 
**created_at** | **datetime** | ISO 8601 UTC timestamp when this record was created. | 
**last_used_at** | **datetime** |  | [optional] 
**expires_at** | **datetime** |  | [optional] 
**quota_requests_per_month_override** | **int** |  | [optional] 
**rate_requests_per_minute_override** | **int** |  | [optional] 
**effective_quota_requests_per_month** | **int** | Effective monthly quota cap for this key. | [optional] [default to 0]
**effective_rate_requests_per_minute** | **int** | Effective requests-per-minute cap for this key. | [optional] [default to 0]

## Example

```python
from cs2cap.models.api_key_info import APIKeyInfo

# TODO update the JSON string below
json = "{}"
# create an instance of APIKeyInfo from a JSON string
api_key_info_instance = APIKeyInfo.from_json(json)
# print the JSON string representation of the object
print(APIKeyInfo.to_json())

# convert the object into a dict
api_key_info_dict = api_key_info_instance.to_dict()
# create an instance of APIKeyInfo from a dict
api_key_info_from_dict = APIKeyInfo.from_dict(api_key_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


