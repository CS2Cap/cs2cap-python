# AccountMutationResponse


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ok** | **bool** | Boolean success indicator for this operation. | 

## Example

```python
from cs2cap.models.account_mutation_response import AccountMutationResponse

# TODO update the JSON string below
json = "{}"
# create an instance of AccountMutationResponse from a JSON string
account_mutation_response_instance = AccountMutationResponse.from_json(json)
# print the JSON string representation of the object
print(AccountMutationResponse.to_json())

# convert the object into a dict
account_mutation_response_dict = account_mutation_response_instance.to_dict()
# create an instance of AccountMutationResponse from a dict
account_mutation_response_from_dict = AccountMutationResponse.from_dict(account_mutation_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


