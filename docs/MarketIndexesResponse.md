# MarketIndexesResponse

Response envelope for /v1/market/indexes.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**MarketIndexesMeta**](MarketIndexesMeta.md) | Response metadata for this payload. | 
**data** | [**MarketIndexesData**](MarketIndexesData.md) | Primary data payload for this response. | 

## Example

```python
from cs2cap.models.market_indexes_response import MarketIndexesResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MarketIndexesResponse from a JSON string
market_indexes_response_instance = MarketIndexesResponse.from_json(json)
# print the JSON string representation of the object
print(MarketIndexesResponse.to_json())

# convert the object into a dict
market_indexes_response_dict = market_indexes_response_instance.to_dict()
# create an instance of MarketIndexesResponse from a dict
market_indexes_response_from_dict = MarketIndexesResponse.from_dict(market_indexes_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


