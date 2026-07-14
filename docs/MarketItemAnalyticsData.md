# MarketItemAnalyticsData

Payload for /v1/market/items/{item_id}.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**summary** | [**MarketItemAnalyticsSummary**](MarketItemAnalyticsSummary.md) | Summary value. | 
**providers** | [**List[MarketItemAnalyticsProvider]**](MarketItemAnalyticsProvider.md) | Providers value. | 
**coverage** | [**MarketItemAnalyticsCoverage**](MarketItemAnalyticsCoverage.md) | Coverage value. | 

## Example

```python
from cs2cap.models.market_item_analytics_data import MarketItemAnalyticsData

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemAnalyticsData from a JSON string
market_item_analytics_data_instance = MarketItemAnalyticsData.from_json(json)
# print the JSON string representation of the object
print(MarketItemAnalyticsData.to_json())

# convert the object into a dict
market_item_analytics_data_dict = market_item_analytics_data_instance.to_dict()
# create an instance of MarketItemAnalyticsData from a dict
market_item_analytics_data_from_dict = MarketItemAnalyticsData.from_dict(market_item_analytics_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


