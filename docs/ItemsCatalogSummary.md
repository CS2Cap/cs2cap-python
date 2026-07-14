# ItemsCatalogSummary


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**total_items** | **int** | Total number of catalog items currently available. | 

## Example

```python
from cs2cap.models.items_catalog_summary import ItemsCatalogSummary

# TODO update the JSON string below
json = "{}"
# create an instance of ItemsCatalogSummary from a JSON string
items_catalog_summary_instance = ItemsCatalogSummary.from_json(json)
# print the JSON string representation of the object
print(ItemsCatalogSummary.to_json())

# convert the object into a dict
items_catalog_summary_dict = items_catalog_summary_instance.to_dict()
# create an instance of ItemsCatalogSummary from a dict
items_catalog_summary_from_dict = ItemsCatalogSummary.from_dict(items_catalog_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


