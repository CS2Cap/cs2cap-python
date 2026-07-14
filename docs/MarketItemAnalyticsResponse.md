# MarketItemAnalyticsResponse

Response envelope for /v1/market/items/{item_id}.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**MarketMeta**](MarketMeta.md) | Response metadata for this payload. | 
**data** | [**MarketItemAnalyticsData**](MarketItemAnalyticsData.md) | Primary data payload for this response. | 

## Example

```python
from cs2cap.models.market_item_analytics_response import MarketItemAnalyticsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MarketItemAnalyticsResponse from a JSON string
market_item_analytics_response_instance = MarketItemAnalyticsResponse.from_json(json)
# print the JSON string representation of the object
print(MarketItemAnalyticsResponse.to_json())

# convert the object into a dict
market_item_analytics_response_dict = market_item_analytics_response_instance.to_dict()
# create an instance of MarketItemAnalyticsResponse from a dict
market_item_analytics_response_from_dict = MarketItemAnalyticsResponse.from_dict(market_item_analytics_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


