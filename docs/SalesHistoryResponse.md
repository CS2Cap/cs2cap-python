# SalesHistoryResponse

Recent Sales response with request metadata.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**SalesMeta**](SalesMeta.md) | Response metadata for this payload. | 
**items** | [**List[SaleRecordDetail]**](SaleRecordDetail.md) | List of returned items. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Cursor pagination footer for this page. | 

## Example

```python
from cs2cap.models.sales_history_response import SalesHistoryResponse

# TODO update the JSON string below
json = "{}"
# create an instance of SalesHistoryResponse from a JSON string
sales_history_response_instance = SalesHistoryResponse.from_json(json)
# print the JSON string representation of the object
print(SalesHistoryResponse.to_json())

# convert the object into a dict
sales_history_response_dict = sales_history_response_instance.to_dict()
# create an instance of SalesHistoryResponse from a dict
sales_history_response_from_dict = SalesHistoryResponse.from_dict(sales_history_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


