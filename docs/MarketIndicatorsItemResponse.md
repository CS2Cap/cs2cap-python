# MarketIndicatorsItemResponse

Response envelope for /v1/market/indicators (individual item mode).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**MarketIndicatorsMeta**](MarketIndicatorsMeta.md) | Response metadata for this payload. | 
**data** | [**MarketIndicatorsItemData**](MarketIndicatorsItemData.md) | Primary data payload for this response. | 

## Example

```python
from cs2cap.models.market_indicators_item_response import MarketIndicatorsItemResponse

# TODO update the JSON string below
json = "{}"
# create an instance of MarketIndicatorsItemResponse from a JSON string
market_indicators_item_response_instance = MarketIndicatorsItemResponse.from_json(json)
# print the JSON string representation of the object
print(MarketIndicatorsItemResponse.to_json())

# convert the object into a dict
market_indicators_item_response_dict = market_indicators_item_response_instance.to_dict()
# create an instance of MarketIndicatorsItemResponse from a dict
market_indicators_item_response_from_dict = MarketIndicatorsItemResponse.from_dict(market_indicators_item_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


