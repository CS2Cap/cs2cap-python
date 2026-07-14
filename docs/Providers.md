# Providers

Provider provenance for composite candle values.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**o** | **str** | Provider key that contributed the returned open value. | [optional] [default to 'unknown']
**h** | **str** | Provider key that contributed the returned high value. | 
**l** | **str** | Provider key that contributed the returned low value. | 
**c** | **str** | Provider key that contributed the returned close value. | [optional] [default to 'unknown']

## Example

```python
from cs2cap.models.providers import Providers

# TODO update the JSON string below
json = "{}"
# create an instance of Providers from a JSON string
providers_instance = Providers.from_json(json)
# print the JSON string representation of the object
print(Providers.to_json())

# convert the object into a dict
providers_dict = providers_instance.to_dict()
# create an instance of Providers from a dict
providers_from_dict = Providers.from_dict(providers_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


