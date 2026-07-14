# IndicatorDataCoverage

Data sufficiency information for computed indicators.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**candle_count** | **int** | Number of candle buckets used for indicator computation. | 
**first_bucket** | **datetime** |  | [optional] 
**last_bucket** | **datetime** |  | [optional] 
**sufficient_for** | **List[str]** | Indicator families with sufficient data coverage. | [optional] 
**insufficient_for** | **List[str]** | Indicator families with insufficient data coverage. | [optional] 

## Example

```python
from cs2cap.models.indicator_data_coverage import IndicatorDataCoverage

# TODO update the JSON string below
json = "{}"
# create an instance of IndicatorDataCoverage from a JSON string
indicator_data_coverage_instance = IndicatorDataCoverage.from_json(json)
# print the JSON string representation of the object
print(IndicatorDataCoverage.to_json())

# convert the object into a dict
indicator_data_coverage_dict = indicator_data_coverage_instance.to_dict()
# create an instance of IndicatorDataCoverage from a dict
indicator_data_coverage_from_dict = IndicatorDataCoverage.from_dict(indicator_data_coverage_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


