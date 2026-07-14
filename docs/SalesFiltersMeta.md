# SalesFiltersMeta

Filter metadata for sales endpoint.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** |  | [optional] 
**market_hash_name** | **str** |  | [optional] 
**phase** | **str** |  | [optional] 
**requested_providers** | **List[str]** |  | [optional] 
**min_float** | **float** |  | [optional] 
**max_float** | **float** |  | [optional] 
**paint_seed** | **int** |  | [optional] 
**stickers** | **List[str]** |  | [optional] 
**charms** | **str** |  | [optional] 
**limit** | **int** | Maximum number of records returned per page. | 

## Example

```python
from cs2cap.models.sales_filters_meta import SalesFiltersMeta

# TODO update the JSON string below
json = "{}"
# create an instance of SalesFiltersMeta from a JSON string
sales_filters_meta_instance = SalesFiltersMeta.from_json(json)
# print the JSON string representation of the object
print(SalesFiltersMeta.to_json())

# convert the object into a dict
sales_filters_meta_dict = sales_filters_meta_instance.to_dict()
# create an instance of SalesFiltersMeta from a dict
sales_filters_meta_from_dict = SalesFiltersMeta.from_dict(sales_filters_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


