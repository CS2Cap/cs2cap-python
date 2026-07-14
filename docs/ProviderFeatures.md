# ProviderFeatures


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**has_buy_orders** | **bool** |  | [optional] 
**has_recent_sales** | **bool** |  | [optional] 

## Example

```python
from cs2cap.models.provider_features import ProviderFeatures

# TODO update the JSON string below
json = "{}"
# create an instance of ProviderFeatures from a JSON string
provider_features_instance = ProviderFeatures.from_json(json)
# print the JSON string representation of the object
print(ProviderFeatures.to_json())

# convert the object into a dict
provider_features_dict = provider_features_instance.to_dict()
# create an instance of ProviderFeatures from a dict
provider_features_from_dict = ProviderFeatures.from_dict(provider_features_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


