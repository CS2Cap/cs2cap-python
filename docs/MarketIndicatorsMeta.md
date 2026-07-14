# MarketIndicatorsMeta

Metadata for indicators endpoint.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**generated_at** | **datetime** | ISO 8601 UTC timestamp when this response was generated. | 
**data_source** | **str** | Primary data source used to build this response. | 
**freshness_sec** | **int** | Estimated freshness of source data in seconds. | 
**window** | [**MarketTimeWindowMeta**](MarketTimeWindowMeta.md) |  | [optional] 
**interval** | **str** | Interval value. | 
**provider** | **str** |  | [optional] 

## Example

```python
from cs2cap.models.market_indicators_meta import MarketIndicatorsMeta

# TODO update the JSON string below
json = "{}"
# create an instance of MarketIndicatorsMeta from a JSON string
market_indicators_meta_instance = MarketIndicatorsMeta.from_json(json)
# print the JSON string representation of the object
print(MarketIndicatorsMeta.to_json())

# convert the object into a dict
market_indicators_meta_dict = market_indicators_meta_instance.to_dict()
# create an instance of MarketIndicatorsMeta from a dict
market_indicators_meta_from_dict = MarketIndicatorsMeta.from_dict(market_indicators_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


