# PortfolioImportResult

Result of an inventory import operation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**imported** | **int** | Items added to the portfolio. | 
**skipped** | **int** | Items already present in the portfolio (by asset ID) — not re-added. | 
**unresolved** | **List[str]** | market_hash_name values that could not be matched to the CS2C catalog. These items were not imported. | 

## Example

```python
from cs2cap.models.portfolio_import_result import PortfolioImportResult

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioImportResult from a JSON string
portfolio_import_result_instance = PortfolioImportResult.from_json(json)
# print the JSON string representation of the object
print(PortfolioImportResult.to_json())

# convert the object into a dict
portfolio_import_result_dict = portfolio_import_result_instance.to_dict()
# create an instance of PortfolioImportResult from a dict
portfolio_import_result_from_dict = PortfolioImportResult.from_dict(portfolio_import_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


