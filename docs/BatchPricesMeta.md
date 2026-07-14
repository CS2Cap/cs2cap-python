# BatchPricesMeta

Response metadata for batch prices.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | **str** | Currency code for all money values in this response. | 
**requested_item_count** | **int** | Number of item IDs in the request. | 
**found_item_count** | **int** | Number of items with at least one price quote. | 
**providers_queried** | **List[str]** | Provider keys queried. | 
**generated_at** | **datetime** | UTC timestamp when this response was generated. | 

## Example

```python
from cs2cap.models.batch_prices_meta import BatchPricesMeta

# TODO update the JSON string below
json = "{}"
# create an instance of BatchPricesMeta from a JSON string
batch_prices_meta_instance = BatchPricesMeta.from_json(json)
# print the JSON string representation of the object
print(BatchPricesMeta.to_json())

# convert the object into a dict
batch_prices_meta_dict = batch_prices_meta_instance.to_dict()
# create an instance of BatchPricesMeta from a dict
batch_prices_meta_from_dict = BatchPricesMeta.from_dict(batch_prices_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


