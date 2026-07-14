# PortfolioListResponse

Response envelope for GET /v1/portfolio.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[PortfolioOut]**](PortfolioOut.md) | User&#39;s portfolios. | 

## Example

```python
from cs2cap.models.portfolio_list_response import PortfolioListResponse

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioListResponse from a JSON string
portfolio_list_response_instance = PortfolioListResponse.from_json(json)
# print the JSON string representation of the object
print(PortfolioListResponse.to_json())

# convert the object into a dict
portfolio_list_response_dict = portfolio_list_response_instance.to_dict()
# create an instance of PortfolioListResponse from a dict
portfolio_list_response_from_dict = PortfolioListResponse.from_dict(portfolio_list_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


