# MarketItemAnalyticsSummary

Quick summary for single-item analytics.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider_count** | **int** | Number of providers with at least one active listing for this item. | 
**best_ask_usd** | **str** |  | [optional] 
**best_bid_usd** | **str** |  | [optional] 
**avg_spread_pct** | **float** |  | [optional] 
**total_volume_24h** | **int** | Alias of sales_1d for backward compatibility. | 
**liquidity** | **int** |  | [optional] 
**supply** | **int** |  | [optional] 
**rank** | **int** |  | [optional] 
**marketcap** | **str** |  | [optional] 
**price_rate_24h** | **float** |  | [optional] 
**price_diff_24h** | **str** |  | [optional] 
**price_rate_7d** | **float** |  | [optional] 
**price_diff_7d** | **str** |  | [optional] 
**price_rate_30d** | **float** |  | [optional] 
**price_diff_30d** | **str** |  | [optional] 
**sales_1d** | **int** | Total depletion activity volume observed over the last 24 hours. | 
**sales_7d** | **int** | Total depletion activity volume observed over the last 7 days. | 
**sales_30d** | **int** | Total depletion activity volume observed over the last 30 days. | 
**steam_sales_7d** | **int** |  | [optional] 
**steam_sales_30d** | **int** |  | [optional] 
**listing_score** | **int** |  | [optional] 
**gap_score** | **int** |  | [optional] 
**volume_score** | **int** |  | [optional] 
**stability_score** | **int** |  | [optional] 
**external_score** | **int** |  | [optional] 
**liquidity_last_updated** | **datetime** |  | [optional] 

## Example

```python
from cs2cap.models.market_item_analytics_summary import MarketItemAnalyticsSummary

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemAnalyticsSummary from a JSON string
market_item_analytics_summary_instance = MarketItemAnalyticsSummary.from_json(json)
# print the JSON string representation of the object
print(MarketItemAnalyticsSummary.to_json())

# convert the object into a dict
market_item_analytics_summary_dict = market_item_analytics_summary_instance.to_dict()
# create an instance of MarketItemAnalyticsSummary from a dict
market_item_analytics_summary_from_dict = MarketItemAnalyticsSummary.from_dict(market_item_analytics_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


