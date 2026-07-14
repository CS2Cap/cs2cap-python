# PortfolioRequestItem

Single item in a portfolio valuation request.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID. | 
**quantity** | **int** | Number of units held. | 

## Example

```python
from cs2cap.models.portfolio_request_item import PortfolioRequestItem

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioRequestItem from a JSON string
portfolio_request_item_instance = PortfolioRequestItem.from_json(json)
# print the JSON string representation of the object
print(PortfolioRequestItem.to_json())

# convert the object into a dict
portfolio_request_item_dict = portfolio_request_item_instance.to_dict()
# create an instance of PortfolioRequestItem from a dict
portfolio_request_item_from_dict = PortfolioRequestItem.from_dict(portfolio_request_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


