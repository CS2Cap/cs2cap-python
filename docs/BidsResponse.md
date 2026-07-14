# BidsResponse

Bids response with metadata and pagination.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**PricesMeta**](PricesMeta.md) | Response metadata for this payload. | 
**items** | [**List[BuyOrderItem]**](BuyOrderItem.md) | List of returned items. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Offset pagination metadata. | 

## Example

```python
from cs2cap.models.bids_response import BidsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of BidsResponse from a JSON string
bids_response_instance = BidsResponse.from_json(json)
# print the JSON string representation of the object
print(BidsResponse.to_json())

# convert the object into a dict
bids_response_dict = bids_response_instance.to_dict()
# create an instance of BidsResponse from a dict
bids_response_from_dict = BidsResponse.from_dict(bids_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


