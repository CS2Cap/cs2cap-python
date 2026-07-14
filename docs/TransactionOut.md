# TransactionOut

A single transaction entry within a portfolio.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Transaction UUID. | 
**item_id** | **int** | Catalog item ID. | 
**market_hash_name** | **str** | Steam market hash name. | 
**phase** | **str** |  | [optional] 
**type** | **str** | Transaction type: &#39;buy&#39; or &#39;sell&#39;. | 
**quantity** | **int** | Number of units. | 
**price** | **int** | Per-unit price in minor units. | 
**fee_amount** | **int** |  | [optional] 
**fee_percentage** | **float** |  | [optional] 
**marketplace** | **str** |  | [optional] 
**var_date** | **date** | Transaction date. | 
**note** | **str** |  | [optional] 
**currency** | **str** | Currency code. | 
**created_at** | **datetime** | When this transaction was recorded. | 
**updated_at** | **datetime** | When this transaction was last modified. | 

## Example

```python
from cs2cap.models.transaction_out import TransactionOut

# TODO update the JSON string below
json = "{}"
# create an instance of TransactionOut from a JSON string
transaction_out_instance = TransactionOut.from_json(json)
# print the JSON string representation of the object
print(TransactionOut.to_json())

# convert the object into a dict
transaction_out_dict = transaction_out_instance.to_dict()
# create an instance of TransactionOut from a dict
transaction_out_from_dict = TransactionOut.from_dict(transaction_out_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


