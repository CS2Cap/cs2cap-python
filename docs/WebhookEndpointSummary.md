# WebhookEndpointSummary

Configured outbound webhook destination.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique webhook destination identifier. | 
**label** | **str** | User-defined label for this destination. | 
**url** | **str** | Destination URL. | 
**platform** | **str** | Delivery platform key for this destination. | 
**secret_last4** | **str** | Last four characters of the current signing secret. | 
**is_active** | **bool** | Whether new events fan out to this destination. | 
**last_success_at** | **datetime** |  | [optional] 
**last_failure_at** | **datetime** |  | [optional] 
**last_failure_message** | **str** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when this destination was created. | 
**updated_at** | **datetime** | ISO 8601 UTC timestamp when this destination was last updated. | 

## Example

```python
from cs2cap.models.webhook_endpoint_summary import WebhookEndpointSummary

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookEndpointSummary from a JSON string
webhook_endpoint_summary_instance = WebhookEndpointSummary.from_json(json)
# print the JSON string representation of the object
print(WebhookEndpointSummary.to_json())

# convert the object into a dict
webhook_endpoint_summary_dict = webhook_endpoint_summary_instance.to_dict()
# create an instance of WebhookEndpointSummary from a dict
webhook_endpoint_summary_from_dict = WebhookEndpointSummary.from_dict(webhook_endpoint_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


