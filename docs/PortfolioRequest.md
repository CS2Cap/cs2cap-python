# PortfolioRequest

Request body for POST /v1/portfolio/value.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**items** | [**List[PortfolioRequestItem]**](PortfolioRequestItem.md) | Items and quantities to value. | 
**currency** | **str** | Target currency code. | [optional] [default to 'USD']
**providers** | **List[str]** |  | [optional] 

## Example

```python
from cs2cap.models.portfolio_request import PortfolioRequest

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioRequest from a JSON string
portfolio_request_instance = PortfolioRequest.from_json(json)
# print the JSON string representation of the object
print(PortfolioRequest.to_json())

# convert the object into a dict
portfolio_request_dict = portfolio_request_instance.to_dict()
# create an instance of PortfolioRequest from a dict
portfolio_request_from_dict = PortfolioRequest.from_dict(portfolio_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


