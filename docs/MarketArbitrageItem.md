# MarketArbitrageItem

Arbitrage opportunity payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**buy_provider** | **str** | Provider offering the best buy-side price for this opportunity. | 
**sell_provider** | **str** | Provider offering the best sell-side price for this opportunity. | 
**buy_price_usd** | **str** | Money amount as a decimal string in USD major units (for example \&quot;25.82\&quot;). | 
**sell_price_usd** | **str** | Money amount as a decimal string in USD major units (for example \&quot;25.82\&quot;). | 
**gross_spread_pct** | **float** | Gross spread percentage. | 
**estimated_fees_usd** | **str** | Money amount as a decimal string in USD major units (for example \&quot;25.82\&quot;). | 
**net_profit_usd** | **str** | Money amount as a decimal string in USD major units (for example \&quot;25.82\&quot;). | 
**last_updated** | **datetime** | ISO 8601 UTC timestamp when this record was last ingested or processed. | 

## Example

```python
from cs2cap.models.market_arbitrage_item import MarketArbitrageItem

# TODO update the JSON string below
json = "{}"
# create an instance of MarketArbitrageItem from a JSON string
market_arbitrage_item_instance = MarketArbitrageItem.from_json(json)
# print the JSON string representation of the object
print(MarketArbitrageItem.to_json())

# convert the object into a dict
market_arbitrage_item_dict = market_arbitrage_item_instance.to_dict()
# create an instance of MarketArbitrageItem from a dict
market_arbitrage_item_from_dict = MarketArbitrageItem.from_dict(market_arbitrage_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


