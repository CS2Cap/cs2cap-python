# SteamInventoryResponse

Response envelope for GET /v1/portfolio/steam-inventory.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[SteamInventoryItem]**](SteamInventoryItem.md) | Items in the inventory. | 
**total_count** | **int** | Total inventory count reported by Steam. | 

## Example

```python
from cs2cap.models.steam_inventory_response import SteamInventoryResponse

# TODO update the JSON string below
json = "{}"
# create an instance of SteamInventoryResponse from a JSON string
steam_inventory_response_instance = SteamInventoryResponse.from_json(json)
# print the JSON string representation of the object
print(SteamInventoryResponse.to_json())

# convert the object into a dict
steam_inventory_response_dict = steam_inventory_response_instance.to_dict()
# create an instance of SteamInventoryResponse from a dict
steam_inventory_response_from_dict = SteamInventoryResponse.from_dict(steam_inventory_response_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


