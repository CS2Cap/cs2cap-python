# MarketItemAnalyticsProvider

Provider-level item analytics payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **str** | Provider key used by this API. | 
**ask_usd** | **str** | Ask price in USD major units. | 
**bid_usd** | **str** |  | [optional] 
**spread_usd** | **str** |  | [optional] 
**spread_pct** | **float** |  | [optional] 
**ask_depth** | **int** |  | [optional] 
**bid_depth** | **int** |  | [optional] 
**volume_24h** | **int** |  | [optional] 
**volume_7d** | **int** |  | [optional] 
**total_value_24h_usd** | **str** |  | [optional] 
**price_rate_24h** | **float** |  | [optional] 
**price_diff_24h** | **str** |  | [optional] 
**price_rate_7d** | **float** |  | [optional] 
**price_diff_7d** | **str** |  | [optional] 
**price_rate_30d** | **float** |  | [optional] 
**price_diff_30d** | **str** |  | [optional] 
**bid_anomaly** | **bool** |  | [optional] 

## Example

```python
from cs2cap.models.market_item_analytics_provider import MarketItemAnalyticsProvider

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemAnalyticsProvider from a JSON string
market_item_analytics_provider_instance = MarketItemAnalyticsProvider.from_json(json)
# print the JSON string representation of the object
print(MarketItemAnalyticsProvider.to_json())

# convert the object into a dict
market_item_analytics_provider_dict = market_item_analytics_provider_instance.to_dict()
# create an instance of MarketItemAnalyticsProvider from a dict
market_item_analytics_provider_from_dict = MarketItemAnalyticsProvider.from_dict(market_item_analytics_provider_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


