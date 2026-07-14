# PricesMeta

Metadata for prices and bids responses.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | **str** | ISO 4217 currency code for the value context. | 
**filters** | [**PricesFilterMeta**](PricesFilterMeta.md) | Effective request filters applied to this response. | 
**providers_queried** | **List[str]** | Provider keys queried. | 

## Example

```python
from cs2cap.models.prices_meta import PricesMeta

# TODO update the JSON string below
json = "{}"
# create an instance of PricesMeta from a JSON string
prices_meta_instance = PricesMeta.from_json(json)
# print the JSON string representation of the object
print(PricesMeta.to_json())

# convert the object into a dict
prices_meta_dict = prices_meta_instance.to_dict()
# create an instance of PricesMeta from a dict
prices_meta_from_dict = PricesMeta.from_dict(prices_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


