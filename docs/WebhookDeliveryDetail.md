# WebhookDeliveryDetail

Detailed view of one webhook delivery job.

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
**payload** | **Dict[str, object]** | Snapshot of the outbound JSON payload. | 
**attempts** | [**List[WebhookDeliveryAttemptSummary]**](WebhookDeliveryAttemptSummary.md) | HTTP delivery attempts recorded for this job. | 

## Example

```python
from cs2cap.models.webhook_delivery_detail import WebhookDeliveryDetail

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookDeliveryDetail from a JSON string
webhook_delivery_detail_instance = WebhookDeliveryDetail.from_json(json)
# print the JSON string representation of the object
print(WebhookDeliveryDetail.to_json())

# convert the object into a dict
webhook_delivery_detail_dict = webhook_delivery_detail_instance.to_dict()
# create an instance of WebhookDeliveryDetail from a dict
webhook_delivery_detail_from_dict = WebhookDeliveryDetail.from_dict(webhook_delivery_detail_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


