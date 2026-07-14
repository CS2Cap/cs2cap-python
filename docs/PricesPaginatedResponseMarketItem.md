# PricesPaginatedResponseMarketItem


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**meta** | [**PricesMeta**](PricesMeta.md) | Response metadata for this payload. | 
**items** | [**List[MarketItem]**](MarketItem.md) | List of returned items. | 
**pagination** | [**PaginationMeta**](PaginationMeta.md) | Pagination metadata for this response. | 

## Example

```python
from cs2cap.models.prices_paginated_response_market_item import PricesPaginatedResponseMarketItem

# TODO update the JSON string below
json = "{}"
# create an instance of PricesPaginatedResponseMarketItem from a JSON string
prices_paginated_response_market_item_instance = PricesPaginatedResponseMarketItem.from_json(json)
# print the JSON string representation of the object
print(PricesPaginatedResponseMarketItem.to_json())

# convert the object into a dict
prices_paginated_response_market_item_dict = prices_paginated_response_market_item_instance.to_dict()
# create an instance of PricesPaginatedResponseMarketItem from a dict
prices_paginated_response_market_item_from_dict = PricesPaginatedResponseMarketItem.from_dict(prices_paginated_response_market_item_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


