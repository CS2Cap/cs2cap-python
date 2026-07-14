# PortfolioCreate

Request body for POST /v1/portfolio.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Display name for this portfolio. | 

## Example

```python
from cs2cap.models.portfolio_create import PortfolioCreate

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioCreate from a JSON string
portfolio_create_instance = PortfolioCreate.from_json(json)
# print the JSON string representation of the object
print(PortfolioCreate.to_json())

# convert the object into a dict
portfolio_create_dict = portfolio_create_instance.to_dict()
# create an instance of PortfolioCreate from a dict
portfolio_create_from_dict = PortfolioCreate.from_dict(portfolio_create_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


