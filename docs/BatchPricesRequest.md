# BatchPricesRequest

Request body for POST /v1/prices/batch.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_ids** | **List[int]** |  | [optional] 
**market_hash_names** | **List[str]** |  | [optional] 
**providers** | **List[str]** |  | [optional] 
**currency** | **str** | Target currency code for returned prices. | [optional] [default to 'USD']

## Example

```python
from cs2cap.models.batch_prices_request import BatchPricesRequest

# TODO update the JSON string below
json = "{}"
# create an instance of BatchPricesRequest from a JSON string
batch_prices_request_instance = BatchPricesRequest.from_json(json)
# print the JSON string representation of the object
print(BatchPricesRequest.to_json())

# convert the object into a dict
batch_prices_request_dict = batch_prices_request_instance.to_dict()
# create an instance of BatchPricesRequest from a dict
batch_prices_request_from_dict = BatchPricesRequest.from_dict(batch_prices_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


