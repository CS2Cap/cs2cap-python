# IndicatorVolume

Volume indicator values.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**vwap** | **float** |  | [optional] 
**obv** | **float** |  | [optional] 
**volume_sma_20** | **float** |  | [optional] 

## Example

```python
from cs2cap.models.indicator_volume import IndicatorVolume

# TODO update the JSON string below
json = "{}"
# create an instance of IndicatorVolume from a JSON string
indicator_volume_instance = IndicatorVolume.from_json(json)
# print the JSON string representation of the object
print(IndicatorVolume.to_json())

# convert the object into a dict
indicator_volume_dict = indicator_volume_instance.to_dict()
# create an instance of IndicatorVolume from a dict
indicator_volume_from_dict = IndicatorVolume.from_dict(indicator_volume_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


