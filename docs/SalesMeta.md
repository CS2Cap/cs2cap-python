# SalesMeta

Metadata for sales response.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | **str** | ISO 4217 currency code for the value context. | 
**filters** | [**SalesFiltersMeta**](SalesFiltersMeta.md) | Effective request filters applied to this response. | 
**providers_queried** | **List[str]** | Provider keys queried while building this response. | 
**result_count** | **int** | Number of records returned in this payload. | 

## Example

```python
from cs2cap.models.sales_meta import SalesMeta

# TODO update the JSON string below
json = "{}"
# create an instance of SalesMeta from a JSON string
sales_meta_instance = SalesMeta.from_json(json)
# print the JSON string representation of the object
print(SalesMeta.to_json())

# convert the object into a dict
sales_meta_dict = sales_meta_instance.to_dict()
# create an instance of SalesMeta from a dict
sales_meta_from_dict = SalesMeta.from_dict(sales_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


