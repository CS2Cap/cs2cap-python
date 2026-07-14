# MarketArbitrageMeta

Metadata for arbitrage endpoint.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**generated_at** | **datetime** | ISO 8601 UTC timestamp when this response was generated. | 
**data_source** | **str** | Primary data source used to build this response. | 
**freshness_sec** | **int** | Estimated freshness of source data in seconds. | 
**window** | [**MarketTimeWindowMeta**](MarketTimeWindowMeta.md) |  | [optional] 

## Example

```python
from cs2cap.models.market_arbitrage_meta import MarketArbitrageMeta

# TODO update the JSON string below
json = "{}"
# create an instance of MarketArbitrageMeta from a JSON string
market_arbitrage_meta_instance = MarketArbitrageMeta.from_json(json)
# print the JSON string representation of the object
print(MarketArbitrageMeta.to_json())

# convert the object into a dict
market_arbitrage_meta_dict = market_arbitrage_meta_instance.to_dict()
# create an instance of MarketArbitrageMeta from a dict
market_arbitrage_meta_from_dict = MarketArbitrageMeta.from_dict(market_arbitrage_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


