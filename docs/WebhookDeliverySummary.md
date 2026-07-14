# WebhookDeliverySummary

Summary of one webhook delivery job.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Unique delivery identifier. | 
**event_id** | **str** | Associated alert event identifier. | 
**endpoint_id** | **str** | Webhook destination identifier. | 
**endpoint_label** | **str** | Snapshot of the destination label used for this delivery. | 
**endpoint_url** | **str** | Snapshot of the destination URL used for this delivery. | 
**platform** | **str** | Snapshot of the delivery platform used for this delivery. | 
**event_type** | **str** | Outbound event type. | 
**status** | **str** | Current delivery status. | 
**attempt_count** | **int** | Number of delivery attempts recorded so far. | 
**last_http_status** | **int** |  | [optional] 
**error** | **str** |  | [optional] 
**next_attempt_at** | **datetime** |  | [optional] 
**created_at** | **datetime** | ISO 8601 UTC timestamp when this delivery was created. | 
**completed_at** | **datetime** |  | [optional] 

## Example

```python
from cs2cap.models.webhook_delivery_summary import WebhookDeliverySummary

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookDeliverySummary from a JSON string
webhook_delivery_summary_instance = WebhookDeliverySummary.from_json(json)
# print the JSON string representation of the object
print(WebhookDeliverySummary.to_json())

# convert the object into a dict
webhook_delivery_summary_dict = webhook_delivery_summary_instance.to_dict()
# create an instance of WebhookDeliverySummary from a dict
webhook_delivery_summary_from_dict = WebhookDeliverySummary.from_dict(webhook_delivery_summary_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


