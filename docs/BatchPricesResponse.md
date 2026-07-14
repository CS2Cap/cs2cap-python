# BatchPricesResponse

Response envelope for POST /v1/prices/batch.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**BatchPricesMeta**](BatchPricesMeta.md) | Response metadata. | 
**items** | [**List[BatchPriceItem]**](BatchPriceItem.md) | Per-item price data. | 
**items_not_found** | **List[int]** | Item IDs with no price data available. | 
**names_not_found** | **List[str]** | Market hash names that could not be resolved to a catalog item. | [optional] 

## Example

```python
from cs2cap.models.batch_prices_response import BatchPricesResponse

# TODO update the JSON string below
json = "{}"
# create an instance of BatchPricesResponse from a JSON string
batch_prices_response_instance = BatchPricesResponse.from_json(json)
# print the JSON string representation of the object
print(BatchPricesResponse.to_json())

# convert the object into a dict
batch_prices_response_dict = batch_prices_response_instance.to_dict()
# create an instance of BatchPricesResponse from a dict
batch_prices_response_from_dict = BatchPricesResponse.from_dict(batch_prices_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


