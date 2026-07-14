# IndicatorMomentum

Momentum indicator values.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**rsi_14** | **float** |  | [optional] 
**macd_line** | **float** |  | [optional] 
**macd_signal** | **float** |  | [optional] 
**macd_histogram** | **float** |  | [optional] 
**sma_20** | **float** |  | [optional] 
**sma_50** | **float** |  | [optional] 
**sma_200** | **float** |  | [optional] 
**ema_12** | **float** |  | [optional] 
**ema_26** | **float** |  | [optional] 
**bb_upper** | **float** |  | [optional] 
**bb_middle** | **float** |  | [optional] 
**bb_lower** | **float** |  | [optional] 

## Example

```python
from cs2cap.models.indicator_momentum import IndicatorMomentum

# TODO update the JSON string below
json = "{}"
# create an instance of IndicatorMomentum from a JSON string
indicator_momentum_instance = IndicatorMomentum.from_json(json)
# print the JSON string representation of the object
print(IndicatorMomentum.to_json())

# convert the object into a dict
indicator_momentum_dict = indicator_momentum_instance.to_dict()
# create an instance of IndicatorMomentum from a dict
indicator_momentum_from_dict = IndicatorMomentum.from_dict(indicator_momentum_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


