# MarketHistoryChartResponse

Response envelope for GET /v1/market/history/chart (Quant only).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**MarketHistoryChartMeta**](MarketHistoryChartMeta.md) | Response metadata for this payload. | 
**series** | [**List[MarketHistoryChartSeries]**](MarketHistoryChartSeries.md) | Per-provider daily price-point series. | [optional] 

## Example

```python
from cs2cap.models.market_history_chart_response import MarketHistoryChartResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MarketHistoryChartResponse from a JSON string
market_history_chart_response_instance = MarketHistoryChartResponse.from_json(json)
# print the JSON string representation of the object
print(MarketHistoryChartResponse.to_json())

# convert the object into a dict
market_history_chart_response_dict = market_history_chart_response_instance.to_dict()
# create an instance of MarketHistoryChartResponse from a dict
market_history_chart_response_from_dict = MarketHistoryChartResponse.from_dict(market_history_chart_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


