# ItemsMetadataResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**catalog** | [**ItemsCatalogSummary**](ItemsCatalogSummary.md) | Catalog summary information. | 
**filters** | [**ItemsFilterMetadata**](ItemsFilterMetadata.md) | Available filter metadata. | 

## Example

```python
from cs2cap.models.items_metadata_response import ItemsMetadataResponse

# TODO update the JSON string below
json = "{}"
# create an instance of ItemsMetadataResponse from a JSON string
items_metadata_response_instance = ItemsMetadataResponse.from_json(json)
# print the JSON string representation of the object
print(ItemsMetadataResponse.to_json())

# convert the object into a dict
items_metadata_response_dict = items_metadata_response_instance.to_dict()
# create an instance of ItemsMetadataResponse from a dict
items_metadata_response_from_dict = ItemsMetadataResponse.from_dict(items_metadata_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


