# PriceSnapshotPage

Paginated price snapshots for raw mode.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**PriceHistoryMeta**](PriceHistoryMeta.md) | Response metadata for this payload. | 
**items** | [**List[PriceSnapshot]**](PriceSnapshot.md) | List of returned items. | 
**pagination** | [**CursorPaginationMeta**](CursorPaginationMeta.md) | Pagination metadata for this response. | 

## Example

```python
from cs2cap.models.price_snapshot_page import PriceSnapshotPage

# TODO update the JSON string below
json = "{}"
# create an instance of PriceSnapshotPage from a JSON string
price_snapshot_page_instance = PriceSnapshotPage.from_json(json)
# print the JSON string representation of the object
print(PriceSnapshotPage.to_json())

# convert the object into a dict
price_snapshot_page_dict = price_snapshot_page_instance.to_dict()
# create an instance of PriceSnapshotPage from a dict
price_snapshot_page_from_dict = PriceSnapshotPage.from_dict(price_snapshot_page_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


