# BatchPriceQuote

Price quote from a single provider for one item.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **str** | Provider key. | 
**lowest_ask** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**lowest_ask_decimal** | **str** |  | [optional] 
**quantity** | **int** | Available quantity at this provider. | 
**timestamp** | **datetime** |  | [optional] 
**last_updated** | **datetime** |  | [optional] 

## Example

```python
from cs2cap.models.batch_price_quote import BatchPriceQuote

# TODO update the JSON string below
json = "{}"
# create an instance of BatchPriceQuote from a JSON string
batch_price_quote_instance = BatchPriceQuote.from_json(json)
# print the JSON string representation of the object
print(BatchPriceQuote.to_json())

# convert the object into a dict
batch_price_quote_dict = batch_price_quote_instance.to_dict()
# create an instance of BatchPriceQuote from a dict
batch_price_quote_from_dict = BatchPriceQuote.from_dict(batch_price_quote_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


