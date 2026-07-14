# PortfolioData

Primary data payload for portfolio valuation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**line_items** | [**List[PortfolioLineItem]**](PortfolioLineItem.md) | Per-item valuation breakdown. | 
**total_value** | **int** | Sum of all item_value fields. Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**items_valued** | **int** | Number of items with a computable value. | 
**items_not_found** | **List[int]** | Item IDs with no price data available. | 

## Example

```python
from cs2cap.models.portfolio_data import PortfolioData

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioData from a JSON string
portfolio_data_instance = PortfolioData.from_json(json)
# print the JSON string representation of the object
print(PortfolioData.to_json())

# convert the object into a dict
portfolio_data_dict = portfolio_data_instance.to_dict()
# create an instance of PortfolioData from a dict
portfolio_data_from_dict = PortfolioData.from_dict(portfolio_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


