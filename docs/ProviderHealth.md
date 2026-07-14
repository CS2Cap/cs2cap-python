# ProviderHealth


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **str** | Health or processing status value. | 
**last_checked_at** | **datetime** |  | [optional] 
**total_offers** | **int** |  | [optional] 
**unique_items** | **int** |  | [optional] 
**market_coverage** | **float** |  | [optional] 
**total_value** | **int** |  | [optional] 
**total_value_usd** | **int** |  | [optional] 

## Example

```python
from cs2cap.models.provider_health import ProviderHealth

# TODO update the JSON string below
json = "{}"
# create an instance of ProviderHealth from a JSON string
provider_health_instance = ProviderHealth.from_json(json)
# print the JSON string representation of the object
print(ProviderHealth.to_json())

# convert the object into a dict
provider_health_dict = provider_health_instance.to_dict()
# create an instance of ProviderHealth from a dict
provider_health_from_dict = ProviderHealth.from_dict(provider_health_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


