# BatchBidQuote

Bid quote from a single provider for one item.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **str** | Provider key. | 
**highest_bid** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**highest_bid_decimal** | **str** |  | [optional] 
**num_bids** | **int** | Number of active buy orders. | 
**timestamp** | **datetime** |  | [optional] 
**last_updated** | **datetime** |  | [optional] 

## Example

```python
from cs2cap.models.batch_bid_quote import BatchBidQuote

# TODO update the JSON string below
json = "{}"
# create an instance of BatchBidQuote from a JSON string
batch_bid_quote_instance = BatchBidQuote.from_json(json)
# print the JSON string representation of the object
print(BatchBidQuote.to_json())

# convert the object into a dict
batch_bid_quote_dict = batch_bid_quote_instance.to_dict()
# create an instance of BatchBidQuote from a dict
batch_bid_quote_from_dict = BatchBidQuote.from_dict(batch_bid_quote_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


