# MarketArbitrageData

Arbitrage endpoint payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**items** | [**List[MarketArbitrageItem]**](MarketArbitrageItem.md) | List of returned items. | 

## Example

```python
from cs2cap.models.market_arbitrage_data import MarketArbitrageData

# TODO update the JSON string below
json = "{}"
# create an instance of MarketArbitrageData from a JSON string
market_arbitrage_data_instance = MarketArbitrageData.from_json(json)
# print the JSON string representation of the object
print(MarketArbitrageData.to_json())

# convert the object into a dict
market_arbitrage_data_dict = market_arbitrage_data_instance.to_dict()
# create an instance of MarketArbitrageData from a dict
market_arbitrage_data_from_dict = MarketArbitrageData.from_dict(market_arbitrage_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


