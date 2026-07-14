# ItemsPaginatedResponseItemOut


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**items** | [**List[ItemOut]**](ItemOut.md) | List of returned items. | 
**pagination** | [**ItemsPaginationMeta**](ItemsPaginationMeta.md) | Pagination metadata for this &#x60;/v1/items&#x60; response. | 

## Example

```python
from cs2cap.models.items_paginated_response_item_out import ItemsPaginatedResponseItemOut

# TODO update the JSON string below
json = "{}"
# create an instance of ItemsPaginatedResponseItemOut from a JSON string
items_paginated_response_item_out_instance = ItemsPaginatedResponseItemOut.from_json(json)
# print the JSON string representation of the object
print(ItemsPaginatedResponseItemOut.to_json())

# convert the object into a dict
items_paginated_response_item_out_dict = items_paginated_response_item_out_instance.to_dict()
# create an instance of ItemsPaginatedResponseItemOut from a dict
items_paginated_response_item_out_from_dict = ItemsPaginatedResponseItemOut.from_dict(items_paginated_response_item_out_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


