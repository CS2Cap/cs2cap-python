# BatchBidsRequest

Request body for POST /v1/bids/batch.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_ids** | **List[int]** |  | [optional] 
**market_hash_names** | **List[str]** |  | [optional] 
**providers** | **List[str]** |  | [optional] 
**currency** | **str** | Target currency code for returned bids. | [optional] [default to 'USD']

## Example

```python
from cs2cap.models.batch_bids_request import BatchBidsRequest

# TODO update the JSON string below
json = "{}"
# create an instance of BatchBidsRequest from a JSON string
batch_bids_request_instance = BatchBidsRequest.from_json(json)
# print the JSON string representation of the object
print(BatchBidsRequest.to_json())

# convert the object into a dict
batch_bids_request_dict = batch_bids_request_instance.to_dict()
# create an instance of BatchBidsRequest from a dict
batch_bids_request_from_dict = BatchBidsRequest.from_dict(batch_bids_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


