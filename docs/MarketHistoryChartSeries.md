# MarketHistoryChartSeries

Per-provider daily price-point series.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **str** | Provider key. | 
**data** | [**List[MarketHistoryChartPoint]**](MarketHistoryChartPoint.md) | Daily points ordered by ascending bucket. | [optional] 

## Example

```python
from cs2cap.models.market_history_chart_series import MarketHistoryChartSeries

# TODO update the JSON string below
json = "{}"
# create an instance of MarketHistoryChartSeries from a JSON string
market_history_chart_series_instance = MarketHistoryChartSeries.from_json(json)
# print the JSON string representation of the object
print(MarketHistoryChartSeries.to_json())

# convert the object into a dict
market_history_chart_series_dict = market_history_chart_series_instance.to_dict()
# create an instance of MarketHistoryChartSeries from a dict
market_history_chart_series_from_dict = MarketHistoryChartSeries.from_dict(market_history_chart_series_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


