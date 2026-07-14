# TransactionCreateRequest

Request body for adding a transaction to a portfolio.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** |  | [optional] 
**market_hash_name** | **str** |  | [optional] 
**phase** | **str** |  | [optional] 
**type** | **str** | Transaction type. | 
**quantity** | **int** | Number of units. | 
**price** | **int** | Per-unit price in minor units (e.g. USD cents). | 
**var_date** | **date** | Transaction date (YYYY-MM-DD). | 
**fee_amount** | **int** |  | [optional] 
**fee_percentage** | **float** |  | [optional] 
**marketplace** | **str** |  | [optional] 
**note** | **str** |  | [optional] 
**currency** | **str** | Currency code. | [optional] [default to 'USD']

## Example

```python
from cs2cap.models.transaction_create_request import TransactionCreateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of TransactionCreateRequest from a JSON string
transaction_create_request_instance = TransactionCreateRequest.from_json(json)
# print the JSON string representation of the object
print(TransactionCreateRequest.to_json())

# convert the object into a dict
transaction_create_request_dict = transaction_create_request_instance.to_dict()
# create an instance of TransactionCreateRequest from a dict
transaction_create_request_from_dict = TransactionCreateRequest.from_dict(transaction_create_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


