# WebhookEndpointsResponse

List of configured outbound webhook destinations.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**webhooks** | [**List[WebhookEndpointSummary]**](WebhookEndpointSummary.md) | Configured webhook destinations. | 

## Example

```python
from cs2cap.models.webhook_endpoints_response import WebhookEndpointsResponse

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookEndpointsResponse from a JSON string
webhook_endpoints_response_instance = WebhookEndpointsResponse.from_json(json)
# print the JSON string representation of the object
print(WebhookEndpointsResponse.to_json())

# convert the object into a dict
webhook_endpoints_response_dict = webhook_endpoints_response_instance.to_dict()
# create an instance of WebhookEndpointsResponse from a dict
webhook_endpoints_response_from_dict = WebhookEndpointsResponse.from_dict(webhook_endpoints_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


