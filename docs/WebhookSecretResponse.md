# WebhookSecretResponse

Response carrying one-time plaintext secret material.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**webhook** | [**WebhookEndpointSummary**](WebhookEndpointSummary.md) | Webhook destination metadata. | 
**secret** | **str** | Plaintext signing secret shown only once. | 

## Example

```python
from cs2cap.models.webhook_secret_response import WebhookSecretResponse

# TODO update the JSON string below
json = "{}"
# create an instance of WebhookSecretResponse from a JSON string
webhook_secret_response_instance = WebhookSecretResponse.from_json(json)
# print the JSON string representation of the object
print(WebhookSecretResponse.to_json())

# convert the object into a dict
webhook_secret_response_dict = webhook_secret_response_instance.to_dict()
# create an instance of WebhookSecretResponse from a dict
webhook_secret_response_from_dict = WebhookSecretResponse.from_dict(webhook_secret_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


