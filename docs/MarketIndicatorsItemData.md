# MarketIndicatorsItemData

Full indicator data for one item (individual mode).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**provider** | **str** | Provider key used by this API. | 
**interval** | **str** | Interval value. | 
**close_price_usd** | **str** | USD-denominated value for close price. | 
**momentum** | [**IndicatorMomentum**](IndicatorMomentum.md) | Momentum value. | 
**volatility** | [**IndicatorVolatility**](IndicatorVolatility.md) | Volatility value. | 
**volume** | [**IndicatorVolume**](IndicatorVolume.md) | Volume value. | 
**signals** | [**IndicatorSignals**](IndicatorSignals.md) | Signals value. | 
**coverage** | [**IndicatorDataCoverage**](IndicatorDataCoverage.md) | Coverage value. | 

## Example

```python
from cs2cap.models.market_indicators_item_data import MarketIndicatorsItemData

# TODO update the JSON string below
json = "{}"
# create an instance of MarketIndicatorsItemData from a JSON string
market_indicators_item_data_instance = MarketIndicatorsItemData.from_json(json)
# print the JSON string representation of the object
print(MarketIndicatorsItemData.to_json())

# convert the object into a dict
market_indicators_item_data_dict = market_indicators_item_data_instance.to_dict()
# create an instance of MarketIndicatorsItemData from a dict
market_indicators_item_data_from_dict = MarketIndicatorsItemData.from_dict(market_indicators_item_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


