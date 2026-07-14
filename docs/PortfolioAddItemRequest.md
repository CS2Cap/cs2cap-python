# PortfolioAddItemRequest

Request body for POST /v1/portfolio/{portfolio_id}/items.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** |  | [optional] 
**market_hash_name** | **str** |  | [optional] 
**phase** | **str** |  | [optional] 
**quantity** | **int** | Number of units to add. | 

## Example

```python
from cs2cap.models.portfolio_add_item_request import PortfolioAddItemRequest

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioAddItemRequest from a JSON string
portfolio_add_item_request_instance = PortfolioAddItemRequest.from_json(json)
# print the JSON string representation of the object
print(PortfolioAddItemRequest.to_json())

# convert the object into a dict
portfolio_add_item_request_dict = portfolio_add_item_request_instance.to_dict()
# create an instance of PortfolioAddItemRequest from a dict
portfolio_add_item_request_from_dict = PortfolioAddItemRequest.from_dict(portfolio_add_item_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


