# CursorPaginationMeta

Cursor pagination metadata for keyset-based endpoints.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | **int** | Items returned per page. | 
**has_next** | **bool** | Whether another page can be requested with &#x60;next_cursor&#x60;. | 
**has_prev** | **bool** | Whether this response was derived from a cursor-aware follow-up request. | 
**next_cursor** | **str** |  | 

## Example

```python
from cs2cap.models.cursor_pagination_meta import CursorPaginationMeta

# TODO update the JSON string below
json = "{}"
# create an instance of CursorPaginationMeta from a JSON string
cursor_pagination_meta_instance = CursorPaginationMeta.from_json(json)
# print the JSON string representation of the object
print(CursorPaginationMeta.to_json())

# convert the object into a dict
cursor_pagination_meta_dict = cursor_pagination_meta_instance.to_dict()
# create an instance of CursorPaginationMeta from a dict
cursor_pagination_meta_from_dict = CursorPaginationMeta.from_dict(cursor_pagination_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


