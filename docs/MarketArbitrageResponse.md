# MarketArbitrageResponse

Response envelope for /v1/market/arbitrage.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**MarketArbitrageMeta**](MarketArbitrageMeta.md) | Response metadata for this payload. | 
**data** | [**MarketArbitrageData**](MarketArbitrageData.md) | Primary data payload for this response. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Cursor pagination metadata. | 

## Example

```python
from cs2cap.models.market_arbitrage_response import MarketArbitrageResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MarketArbitrageResponse from a JSON string
market_arbitrage_response_instance = MarketArbitrageResponse.from_json(json)
# print the JSON string representation of the object
print(MarketArbitrageResponse.to_json())

# convert the object into a dict
market_arbitrage_response_dict = market_arbitrage_response_instance.to_dict()
# create an instance of MarketArbitrageResponse from a dict
market_arbitrage_response_from_dict = MarketArbitrageResponse.from_dict(market_arbitrage_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


