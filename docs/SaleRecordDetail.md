# SaleRecordDetail

Sale record matching CSFloat API response format.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**var_date** | **datetime** | ISO 8601 UTC timestamp for this event. | 
**provider** | **str** | Provider key used by this API. | 
**price** | **int** | Money amount in minor units of the response currency (for example USD cents when currency&#x3D;USD). Divide by 100 for display. | 
**currency** | **str** | ISO 4217 currency code for the value context. | 
**item_id** | **int** | Normalized catalog item ID used by this API. | 
**market_hash_name** | **str** | Canonical Steam market hash name for the item. | 
**phase** | **str** |  | [optional] 
**var_float** | **float** |  | [optional] 
**paint_seed** | **int** |  | [optional] 
**stickers** | [**List[StickerInfo]**](StickerInfo.md) |  | [optional] 
**charms** | [**List[CharmInfo]**](CharmInfo.md) |  | [optional] 
**inspect** | [**InspectInfo**](InspectInfo.md) |  | [optional] 

## Example

```python
from cs2cap.models.sale_record_detail import SaleRecordDetail

# TODO update the JSON string below
json = "{}"
# create an instance of SaleRecordDetail from a JSON string
sale_record_detail_instance = SaleRecordDetail.from_json(json)
# print the JSON string representation of the object
print(SaleRecordDetail.to_json())

# convert the object into a dict
sale_record_detail_dict = sale_record_detail_instance.to_dict()
# create an instance of SaleRecordDetail from a dict
sale_record_detail_from_dict = SaleRecordDetail.from_dict(sale_record_detail_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


