# PriceCandlesPage

Candle response for a requested time window.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**PriceCandlesMeta**](PriceCandlesMeta.md) | Response metadata for this payload. | 
**data** | [**List[PriceCandleItem]**](PriceCandleItem.md) | Primary data payload for this response. | 

## Example

```python
from cs2cap.models.price_candles_page import PriceCandlesPage

# TODO update the JSON string below
json = "{}"
# create an instance of PriceCandlesPage from a JSON string
price_candles_page_instance = PriceCandlesPage.from_json(json)
# print the JSON string representation of the object
print(PriceCandlesPage.to_json())

# convert the object into a dict
price_candles_page_dict = price_candles_page_instance.to_dict()
# create an instance of PriceCandlesPage from a dict
price_candles_page_from_dict = PriceCandlesPage.from_dict(price_candles_page_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


