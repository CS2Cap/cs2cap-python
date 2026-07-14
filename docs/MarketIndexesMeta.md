# MarketIndexesMeta

Metadata for /v1/market/indexes.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**generated_at** | **datetime** | ISO 8601 UTC timestamp when this response was generated. | 
**data_source** | **str** | Primary data source used to build this response. | 
**freshness_sec** | **int** | Estimated freshness of source data in seconds. | 
**window** | [**MarketTimeWindowMeta**](MarketTimeWindowMeta.md) |  | [optional] 
**group_by** | **str** | Catalog dimension used to group market items. | 

## Example

```python
from cs2cap.models.market_indexes_meta import MarketIndexesMeta

# TODO update the JSON string below
json = "{}"
# create an instance of MarketIndexesMeta from a JSON string
market_indexes_meta_instance = MarketIndexesMeta.from_json(json)
# print the JSON string representation of the object
print(MarketIndexesMeta.to_json())

# convert the object into a dict
market_indexes_meta_dict = market_indexes_meta_instance.to_dict()
# create an instance of MarketIndexesMeta from a dict
market_indexes_meta_from_dict = MarketIndexesMeta.from_dict(market_indexes_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


