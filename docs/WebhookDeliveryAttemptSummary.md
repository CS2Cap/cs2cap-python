# WebhookDeliveryAttemptSummary

One outbound webhook HTTP attempt.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**attempt_number** | **int** | One-based attempt number for this delivery. | 
**status** | **str** | Attempt outcome status. | 
**http_status** | **int** |  | [optional] 
**error** | **str** |  | [optional] 
**response_body_excerpt** | **str** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when this attempt was recorded. | 

## Example

```python
from cs2cap.models.webhook_delivery_attempt_summary import WebhookDeliveryAttemptSummary

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookDeliveryAttemptSummary from a JSON string
webhook_delivery_attempt_summary_instance = WebhookDeliveryAttemptSummary.from_json(json)
# print the JSON string representation of the object
print(WebhookDeliveryAttemptSummary.to_json())

# convert the object into a dict
webhook_delivery_attempt_summary_dict = webhook_delivery_attempt_summary_instance.to_dict()
# create an instance of WebhookDeliveryAttemptSummary from a dict
webhook_delivery_attempt_summary_from_dict = WebhookDeliveryAttemptSummary.from_dict(webhook_delivery_attempt_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


