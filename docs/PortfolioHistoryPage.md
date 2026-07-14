# PortfolioHistoryPage

Response envelope for GET /v1/portfolio/{portfolio_id}/history.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**PortfolioHistoryMeta**](PortfolioHistoryMeta.md) | Response metadata. | 
**data** | [**List[PortfolioHistoryPoint]**](PortfolioHistoryPoint.md) | Ordered daily valuation points. | 
**pagination** | [**CursorPaginationMeta**](CursorPaginationMeta.md) | Cursor pagination metadata. | 

## Example

```python
from cs2cap.models.portfolio_history_page import PortfolioHistoryPage

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioHistoryPage from a JSON string
portfolio_history_page_instance = PortfolioHistoryPage.from_json(json)
# print the JSON string representation of the object
print(PortfolioHistoryPage.to_json())

# convert the object into a dict
portfolio_history_page_dict = portfolio_history_page_instance.to_dict()
# create an instance of PortfolioHistoryPage from a dict
portfolio_history_page_from_dict = PortfolioHistoryPage.from_dict(portfolio_history_page_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


