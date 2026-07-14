# ItemsPaginationMeta

Pagination metadata for `/v1/items` full-catalog responses.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**limit** | **int** | Items included in this response window. When &#x60;/v1/items&#x60; is called without a &#x60;limit&#x60;, this equals the number of returned items and may exceed 1000. | 
**offset** | **int** | Starting position | 
**total** | **int** | Total matching catalog items available. | 
**has_next** | **bool** | More items available after current page | 
**has_prev** | **bool** | Items available before current page | 
**next_cursor** | **str** |  | [optional] 

## Example

```python
from cs2cap.models.items_pagination_meta import ItemsPaginationMeta

# TODO update the JSON string below
json = "{}"
# create an instance of ItemsPaginationMeta from a JSON string
items_pagination_meta_instance = ItemsPaginationMeta.from_json(json)
# print the JSON string representation of the object
print(ItemsPaginationMeta.to_json())

# convert the object into a dict
items_pagination_meta_dict = items_pagination_meta_instance.to_dict()
# create an instance of ItemsPaginationMeta from a dict
items_pagination_meta_from_dict = ItemsPaginationMeta.from_dict(items_pagination_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


