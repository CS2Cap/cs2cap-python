# MarketIndexesData

Payload for /v1/market/indexes.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_marketcap_usd** | **str** | Money amount as a decimal string in USD major units (for example \&quot;25.82\&quot;). | 
**groups** | [**List[MarketIndexGroup]**](MarketIndexGroup.md) | Category groups sorted by market cap descending. | 

## Example

```python
from cs2cap.models.market_indexes_data import MarketIndexesData

# TODO update the JSON string below
json = "{}"
# create an instance of MarketIndexesData from a JSON string
market_indexes_data_instance = MarketIndexesData.from_json(json)
# print the JSON string representation of the object
print(MarketIndexesData.to_json())

# convert the object into a dict
market_indexes_data_dict = market_indexes_data_instance.to_dict()
# create an instance of MarketIndexesData from a dict
market_indexes_data_from_dict = MarketIndexesData.from_dict(market_indexes_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


