# MarketMeta

Shared metadata for redesigned market endpoints.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**generated_at** | **datetime** | ISO 8601 UTC timestamp when this response was generated. | 
**data_source** | **str** | Primary data source used to build this response. | 
**freshness_sec** | **int** | Estimated freshness of source data in seconds. | 
**window** | [**MarketTimeWindowMeta**](MarketTimeWindowMeta.md) |  | [optional] 

## Example

```python
from cs2cap.models.market_meta import MarketMeta

# TODO update the JSON string below
json = "{}"
# create an instance of MarketMeta from a JSON string
market_meta_instance = MarketMeta.from_json(json)
# print the JSON string representation of the object
print(MarketMeta.to_json())

# convert the object into a dict
market_meta_dict = market_meta_instance.to_dict()
# create an instance of MarketMeta from a dict
market_meta_from_dict = MarketMeta.from_dict(market_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


