# MarketItemAnalyticsCoverage

Coverage diagnostics for single-item analytics.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider_count** | **int** | Number of providers with at least one active listing for this item. | 
**providers_with_volume** | **int** | Providers with depletion activity volume data. | 
**providers_with_bid_side** | **int** | Providers with bid side value. | 

## Example

```python
from cs2cap.models.market_item_analytics_coverage import MarketItemAnalyticsCoverage

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemAnalyticsCoverage from a JSON string
market_item_analytics_coverage_instance = MarketItemAnalyticsCoverage.from_json(json)
# print the JSON string representation of the object
print(MarketItemAnalyticsCoverage.to_json())

# convert the object into a dict
market_item_analytics_coverage_dict = market_item_analytics_coverage_instance.to_dict()
# create an instance of MarketItemAnalyticsCoverage from a dict
market_item_analytics_coverage_from_dict = MarketItemAnalyticsCoverage.from_dict(market_item_analytics_coverage_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


