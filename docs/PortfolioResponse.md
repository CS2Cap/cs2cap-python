# PortfolioResponse

Response envelope for POST /v1/portfolio/value.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**PortfolioMeta**](PortfolioMeta.md) | Response metadata. | 
**data** | [**PortfolioData**](PortfolioData.md) | Valuation data. | 

## Example

```python
from cs2cap.models.portfolio_response import PortfolioResponse

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioResponse from a JSON string
portfolio_response_instance = PortfolioResponse.from_json(json)
# print the JSON string representation of the object
print(PortfolioResponse.to_json())

# convert the object into a dict
portfolio_response_dict = portfolio_response_instance.to_dict()
# create an instance of PortfolioResponse from a dict
portfolio_response_from_dict = PortfolioResponse.from_dict(portfolio_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


