# PriceCandleItem

Single OHLCV candle data point (time-varying fields only).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**t** | **int** | Unix timestamp in seconds (UTC). | 
**o** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**h** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**l** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**c** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**v** | **int** | Estimated trade volume for the bucket, derived from inventory changes rather than reported sale counts, not transaction volume. | 
**q** | **int** |  | [optional] 
**providers** | [**Providers**](Providers.md) | Provider provenance for the returned open/high/low/close values in this composite candle. | 

## Example

```python
from cs2cap.models.price_candle_item import PriceCandleItem

# TODO update the JSON string below
json = "{}"
# create an instance of PriceCandleItem from a JSON string
price_candle_item_instance = PriceCandleItem.from_json(json)
# print the JSON string representation of the object
print(PriceCandleItem.to_json())

# convert the object into a dict
price_candle_item_dict = price_candle_item_instance.to_dict()
# create an instance of PriceCandleItem from a dict
price_candle_item_from_dict = PriceCandleItem.from_dict(price_candle_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


