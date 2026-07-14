# MarketHistoryChartPoint

One daily price point for a provider series.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**t** | **int** | UTC day bucket as a Unix timestamp (seconds, midnight). | 
**price** | **int** | Closing price in minor units of the response currency. | 
**qty** | **int** |  | [optional] 

## Example

```python
from cs2cap.models.market_history_chart_point import MarketHistoryChartPoint

# TODO update the JSON string below
json = "{}"
# create an instance of MarketHistoryChartPoint from a JSON string
market_history_chart_point_instance = MarketHistoryChartPoint.from_json(json)
# print the JSON string representation of the object
print(MarketHistoryChartPoint.to_json())

# convert the object into a dict
market_history_chart_point_dict = market_history_chart_point_instance.to_dict()
# create an instance of MarketHistoryChartPoint from a dict
market_history_chart_point_from_dict = MarketHistoryChartPoint.from_dict(market_history_chart_point_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


