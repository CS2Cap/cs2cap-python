# MarketHistoryChartMeta

Metadata for /v1/market/history/chart.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID. | 
**market_hash_name** | **str** | Canonical market hash name for the item. | 
**currency** | **str** | Target currency code for returned prices. | 
**start** | **datetime** | ISO 8601 UTC start of the returned window. | 
**end** | **datetime** | ISO 8601 UTC end of the returned window. | 
**providers** | **List[str]** | Provider keys actually returned (those with &gt;&#x3D;1 point in range). | [optional] 

## Example

```python
from cs2cap.models.market_history_chart_meta import MarketHistoryChartMeta

# TODO update the JSON string below
json = "{}"
# create an instance of MarketHistoryChartMeta from a JSON string
market_history_chart_meta_instance = MarketHistoryChartMeta.from_json(json)
# print the JSON string representation of the object
print(MarketHistoryChartMeta.to_json())

# convert the object into a dict
market_history_chart_meta_dict = market_history_chart_meta_instance.to_dict()
# create an instance of MarketHistoryChartMeta from a dict
market_history_chart_meta_from_dict = MarketHistoryChartMeta.from_dict(market_history_chart_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


