# MarketIndexGroup

Single group row for /v1/market/indexes.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**group** | **str** | Catalog category label for this group. | 
**marketcap_usd** | **str** | Money amount as a decimal string in USD major units (for example \&quot;25.82\&quot;). | 
**item_count** | **int** | Snapshot items in this category with a group label. | 
**included_count** | **int** | Items included in market cap aggregation after validation filters. | 
**excluded_count** | **int** | Items excluded because price/bid/marketcap data was incomplete or spread was too high. | 

## Example

```python
from cs2cap.models.market_index_group import MarketIndexGroup

# TODO update the JSON string below
json = "{}"
# create an instance of MarketIndexGroup from a JSON string
market_index_group_instance = MarketIndexGroup.from_json(json)
# print the JSON string representation of the object
print(MarketIndexGroup.to_json())

# convert the object into a dict
market_index_group_dict = market_index_group_instance.to_dict()
# create an instance of MarketIndexGroup from a dict
market_index_group_from_dict = MarketIndexGroup.from_dict(market_index_group_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


