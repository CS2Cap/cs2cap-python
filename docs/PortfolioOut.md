# PortfolioOut

Summary of a saved portfolio.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Portfolio UUID. | 
**name** | **str** | Display name. | 
**item_count** | **int** | Number of items currently in the portfolio. | 
**created_at** | **datetime** | When the portfolio was created. | 
**updated_at** | **datetime** | When the portfolio was last modified. | 

## Example

```python
from cs2cap.models.portfolio_out import PortfolioOut

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioOut from a JSON string
portfolio_out_instance = PortfolioOut.from_json(json)
# print the JSON string representation of the object
print(PortfolioOut.to_json())

# convert the object into a dict
portfolio_out_dict = portfolio_out_instance.to_dict()
# create an instance of PortfolioOut from a dict
portfolio_out_from_dict = PortfolioOut.from_dict(portfolio_out_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


