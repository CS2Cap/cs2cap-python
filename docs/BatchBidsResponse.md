# BatchBidsResponse

Response envelope for POST /v1/bids/batch.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**BatchBidsMeta**](BatchBidsMeta.md) | Response metadata. | 
**items** | [**List[BatchBidItem]**](BatchBidItem.md) | Per-item bid data. | 
**items_not_found** | **List[int]** | Item IDs with no bid data available. | 
**names_not_found** | **List[str]** | Market hash names that could not be resolved to a catalog item. | [optional] 

## Example

```python
from cs2cap.models.batch_bids_response import BatchBidsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of BatchBidsResponse from a JSON string
batch_bids_response_instance = BatchBidsResponse.from_json(json)
# print the JSON string representation of the object
print(BatchBidsResponse.to_json())

# convert the object into a dict
batch_bids_response_dict = batch_bids_response_instance.to_dict()
# create an instance of BatchBidsResponse from a dict
batch_bids_response_from_dict = BatchBidsResponse.from_dict(batch_bids_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


