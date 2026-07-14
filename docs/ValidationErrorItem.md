# ValidationErrorItem

Single validation error entry returned by FastAPI/Pydantic.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **str** | Validation error type (e.g., enum, greater_than) | 
**loc** | [**List[LocInner]**](LocInner.md) | Location of the error (e.g., [&#39;query&#39;, &#39;limit&#39;]) | 
**msg** | **str** | Human-readable validation message | 
**input** | **object** |  | [optional] 
**ctx** | **Dict[str, object]** |  | [optional] 

## Example

```python
from cs2cap.models.validation_error_item import ValidationErrorItem

# TODO update the JSON string below
json = "{}"
# create an instance of ValidationErrorItem from a JSON string
validation_error_item_instance = ValidationErrorItem.from_json(json)
# print the JSON string representation of the object
print(ValidationErrorItem.to_json())

# convert the object into a dict
validation_error_item_dict = validation_error_item_instance.to_dict()
# create an instance of ValidationErrorItem from a dict
validation_error_item_from_dict = ValidationErrorItem.from_dict(validation_error_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


