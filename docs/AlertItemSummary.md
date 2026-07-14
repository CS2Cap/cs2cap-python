# AlertItemSummary

Item metadata attached to an alert.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**item_id** | **int** | Normalized catalog item ID. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 

## Example

```python
from cs2cap.models.alert_item_summary import AlertItemSummary

# TODO update the JSON string below
json = "{}"
# create an instance of AlertItemSummary from a JSON string
alert_item_summary_instance = AlertItemSummary.from_json(json)
# print the JSON string representation of the object
print(AlertItemSummary.to_json())

# convert the object into a dict
alert_item_summary_dict = alert_item_summary_instance.to_dict()
# create an instance of AlertItemSummary from a dict
alert_item_summary_from_dict = AlertItemSummary.from_dict(alert_item_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


