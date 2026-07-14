# PaginationMeta

Unified pagination metadata for all list endpoints.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | **int** | Items per page | 
**offset** | **int** | Starting position | 
**total** | **int** | Total items available. Cursor-based endpoints may return &#x60;-1&#x60; when the total count is intentionally skipped for performance. | 
**has_next** | **bool** | More items available after current page | 
**has_prev** | **bool** | Items available before current page | 
**next_cursor** | **str** |  | [optional] 

## Example

```python
from cs2cap.models.pagination_meta import PaginationMeta

# TODO update the JSON string below
json = "{}"
# create an instance of PaginationMeta from a JSON string
pagination_meta_instance = PaginationMeta.from_json(json)
# print the JSON string representation of the object
print(PaginationMeta.to_json())

# convert the object into a dict
pagination_meta_dict = pagination_meta_instance.to_dict()
# create an instance of PaginationMeta from a dict
pagination_meta_from_dict = PaginationMeta.from_dict(pagination_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


