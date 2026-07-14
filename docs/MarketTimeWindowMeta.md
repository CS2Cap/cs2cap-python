# MarketTimeWindowMeta

Preset time window used for the analytics query.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**timeframe** | **str** | Liquidity scoring horizon used for this query. Controls which depletion volume window (24h, 7d, or 30d) feeds the liquidity volume score. Does not affect price change fields, bid/ask values, spread, or trade counts. | 

## Example

```python
from cs2cap.models.market_time_window_meta import MarketTimeWindowMeta

# TODO update the JSON string below
json = "{}"
# create an instance of MarketTimeWindowMeta from a JSON string
market_time_window_meta_instance = MarketTimeWindowMeta.from_json(json)
# print the JSON string representation of the object
print(MarketTimeWindowMeta.to_json())

# convert the object into a dict
market_time_window_meta_dict = market_time_window_meta_instance.to_dict()
# create an instance of MarketTimeWindowMeta from a dict
market_time_window_meta_from_dict = MarketTimeWindowMeta.from_dict(market_time_window_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


