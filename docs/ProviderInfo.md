# ProviderInfo


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | **str** | Stable provider key used in request and response payloads. | 
**logo** | **str** | CDN URL for the provider logo asset. | 
**code** | **str** |  | [optional] 
**market_type** | **str** |  | [optional] 
**default_currency** | **str** |  | [optional] 
**fees** | [**ProviderFees**](ProviderFees.md) | Fee configuration values keyed by fee type. | 
**features** | [**ProviderFeatures**](ProviderFeatures.md) | Feature capability flags for this provider. | 
**health** | [**ProviderHealth**](ProviderHealth.md) | Provider health metrics and aggregate diagnostics. | 

## Example

```python
from cs2cap.models.provider_info import ProviderInfo

# TODO update the JSON string below
json = "{}"
# create an instance of ProviderInfo from a JSON string
provider_info_instance = ProviderInfo.from_json(json)
# print the JSON string representation of the object
print(ProviderInfo.to_json())

# convert the object into a dict
provider_info_dict = provider_info_instance.to_dict()
# create an instance of ProviderInfo from a dict
provider_info_from_dict = ProviderInfo.from_dict(provider_info_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


