# IndicatorVolatility

Volatility indicator values.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**atr_14** | **float** |  | [optional] 
**historical_volatility_20** | **float** |  | [optional] 
**kc_upper** | **float** |  | [optional] 
**kc_middle** | **float** |  | [optional] 
**kc_lower** | **float** |  | [optional] 

## Example

```python
from cs2cap.models.indicator_volatility import IndicatorVolatility

# TODO update the JSON string below
json = "{}"
# create an instance of IndicatorVolatility from a JSON string
indicator_volatility_instance = IndicatorVolatility.from_json(json)
# print the JSON string representation of the object
print(IndicatorVolatility.to_json())

# convert the object into a dict
indicator_volatility_dict = indicator_volatility_instance.to_dict()
# create an instance of IndicatorVolatility from a dict
indicator_volatility_from_dict = IndicatorVolatility.from_dict(indicator_volatility_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


