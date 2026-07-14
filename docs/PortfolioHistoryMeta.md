# PortfolioHistoryMeta

Metadata for saved-portfolio historical valuation.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**portfolio_id** | **str** | Portfolio UUID. | 
**currency** | **str** | Currency code for all money values. | 
**providers_queried** | **List[str]** | Provider keys queried. | 
**start_date** | **date** | Inclusive UTC start date for the requested window. | 
**end_date** | **date** | Inclusive UTC end date for the requested window. | 
**interval** | **str** | History interval. Always &#x60;1d&#x60;. | [optional] [default to '1d']
**holdings_basis** | **str** | Holdings basis. &#x60;ledger_close&#x60; replays holdings from the transaction ledger; &#x60;current_holdings&#x60; values the portfolio&#39;s current holdings flat across the window (no transactions required). | [optional] [default to 'ledger_close']
**valuation_basis** | **str** | Valuation basis. Always &#x60;best_provider_close&#x60;. | [optional] [default to 'best_provider_close']

## Example

```python
from cs2cap.models.portfolio_history_meta import PortfolioHistoryMeta

# TODO update the JSON string below
json = "{}"
# create an instance of PortfolioHistoryMeta from a JSON string
portfolio_history_meta_instance = PortfolioHistoryMeta.from_json(json)
# print the JSON string representation of the object
print(PortfolioHistoryMeta.to_json())

# convert the object into a dict
portfolio_history_meta_dict = portfolio_history_meta_instance.to_dict()
# create an instance of PortfolioHistoryMeta from a dict
portfolio_history_meta_from_dict = PortfolioHistoryMeta.from_dict(portfolio_history_meta_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


