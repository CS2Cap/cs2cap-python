# IndicatorSignals

Derived signal labels from indicator values.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**rsi** | **str** |  | [optional] 
**macd** | **str** |  | [optional] 
**trend** | **str** |  | [optional] 
**bollinger** | **str** |  | [optional] 
**volatility** | **str** |  | [optional] 
**composite_score** | **float** |  | [optional] 

## Example

```python
from cs2cap.models.indicator_signals import IndicatorSignals

# TODO update the JSON string below
json = "{}"
# create an instance of IndicatorSignals from a JSON string
indicator_signals_instance = IndicatorSignals.from_json(json)
# print the JSON string representation of the object
print(IndicatorSignals.to_json())

# convert the object into a dict
indicator_signals_dict = indicator_signals_instance.to_dict()
# create an instance of IndicatorSignals from a dict
indicator_signals_from_dict = IndicatorSignals.from_dict(indicator_signals_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


