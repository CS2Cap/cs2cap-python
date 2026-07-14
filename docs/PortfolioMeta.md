# PortfolioMeta

Response metadata for portfolio valuation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | **str** | Currency code for all money values. | 
**generated_at** | **datetime** | UTC timestamp when this response was generated. | 
**providers_queried** | **List[str]** | Provider keys queried. | 

## Example

```python
from cs2cap.models.portfolio_meta import PortfolioMeta

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioMeta from a JSON string
portfolio_meta_instance = PortfolioMeta.from_json(json)
# print the JSON string representation of the object
print(PortfolioMeta.to_json())

# convert the object into a dict
portfolio_meta_dict = portfolio_meta_instance.to_dict()
# create an instance of PortfolioMeta from a dict
portfolio_meta_from_dict = PortfolioMeta.from_dict(portfolio_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


