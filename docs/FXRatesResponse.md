# FXRatesResponse

FX rates response - returns USD to X conversion rates.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**timestamp** | **datetime** |  | [optional] 
**rates** | **Dict[str, float]** | Rates value. | 

## Example

```python
from cs2cap.models.fx_rates_response import FXRatesResponse

# TODO update the JSON string below
json = "{}"
# create an instance of FXRatesResponse from a JSON string
fx_rates_response_instance = FXRatesResponse.from_json(json)
# print the JSON string representation of the object
print(FXRatesResponse.to_json())

# convert the object into a dict
fx_rates_response_dict = fx_rates_response_instance.to_dict()
# create an instance of FXRatesResponse from a dict
fx_rates_response_from_dict = FXRatesResponse.from_dict(fx_rates_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


