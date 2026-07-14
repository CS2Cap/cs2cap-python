# ProviderFees


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**sell_fee** | **float** |  | [optional] 
**insta_sell_fee** | **float** |  | [optional] 
**trading_spread_fee** | **float** |  | [optional] 

## Example

```python
from cs2cap.models.provider_fees import ProviderFees

# TODO update the JSON string below
json = "{}"
# create an instance of ProviderFees from a JSON string
provider_fees_instance = ProviderFees.from_json(json)
# print the JSON string representation of the object
print(ProviderFees.to_json())

# convert the object into a dict
provider_fees_dict = provider_fees_instance.to_dict()
# create an instance of ProviderFees from a dict
provider_fees_from_dict = ProviderFees.from_dict(provider_fees_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


