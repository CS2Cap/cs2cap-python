# PortfolioHistoryPoint

One daily historical portfolio valuation point.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**var_date** | **date** | UTC calendar day represented by this point. | 
**total_value** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**positions** | **int** | Distinct portfolio positions with positive holdings. | 
**items_valued** | **int** | Positions included in total_value for the day. | 
**items_missing_price** | **int** | Positions with holdings but no usable price for the day. | 

## Example

```python
from cs2cap.models.portfolio_history_point import PortfolioHistoryPoint

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioHistoryPoint from a JSON string
portfolio_history_point_instance = PortfolioHistoryPoint.from_json(json)
# print the JSON string representation of the object
print(PortfolioHistoryPoint.to_json())

# convert the object into a dict
portfolio_history_point_dict = portfolio_history_point_instance.to_dict()
# create an instance of PortfolioHistoryPoint from a dict
portfolio_history_point_from_dict = PortfolioHistoryPoint.from_dict(portfolio_history_point_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


