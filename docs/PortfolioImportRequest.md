# PortfolioImportRequest

Request body for POST /v1/portfolio/{portfolio_id}/import.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**asset_ids** | **List[str]** |  | [optional] 

## Example

```python
from cs2cap.models.portfolio_import_request import PortfolioImportRequest

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioImportRequest from a JSON string
portfolio_import_request_instance = PortfolioImportRequest.from_json(json)
# print the JSON string representation of the object
print(PortfolioImportRequest.to_json())

# convert the object into a dict
portfolio_import_request_dict = portfolio_import_request_instance.to_dict()
# create an instance of PortfolioImportRequest from a dict
portfolio_import_request_from_dict = PortfolioImportRequest.from_dict(portfolio_import_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


