# 

Move your app forward with the Uber API



## Server Configuration for Base URLs

This section provides details on the environments available and lists down the servers in each of the environment. The default environment for this API is set to `production` while the default server is set to `default`.
### Environments

An environment consists of a set of servers with base URL values. The environment can be changed programatically allowing rapid switching between different environments e.g.the user can specify a Production and Testing Environment.The available environments for this API are: 

#### production
The environment comprises of the following servers: 

| Name | Base URL | 
|-----------|-------------|
| default | https://api.uber.com/ |
| auth | http://auth.example.com/{templateParam} |

#### testing
The environment comprises of the following servers: 

| Name | Base URL | 
|-----------|-------------|
| default | http://uber.example.com/testing |
| auth | http://uberauth.example.com/testing |



### Base URL Parameters
Base URL contains the following parameters:

| Name | Type | Tags | Description | Default Value | 
|------|------| ---- | ----------- | ------------- |
| templateParam | `templateParam` |  ``` Optional ```  | TODO: Add a parameter description | `abc` |





# <a name="api_reference"></a>API Reference

* [User](#user)
* [Estimates](#estimates)
* [Products](#products)

## <a name="user"></a>![Endpoint Group: ](https://apidocs.io/img/class.png "User") User


### <a name="history"></a>![Endpoint: ](https://apidocs.io/img/method.png "History") `GET` /history

> *Tags:*  ``` Skips Authentication ``` 

> User Activity



#### Query Parameters
| Parameter | Type | Tags | Description | Example |
|-----------|------| ---- |-------------| ------- |
| offset | `number` |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. | `2` | 
| limit | `number` |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. | `10` | 

#### Responses
**200** 

> History information for the given user
Body (_Activities_) 
```
{
  "offset": 2,
  "limit": 10,
  "count": 3,
  "history": []
}
```


**Default** 

> Unexpected error
Body (_Error_Error_) 
```
{
  "code": 164,
  "message": "message",
  "fields": "fields"
}
```


### <a name="me"></a>![Endpoint: ](https://apidocs.io/img/method.png "Me") `GET` /me

> *Tags:*  ``` Skips Authentication ``` 

> User Profile



#### Responses
**200** 

> Profile information for a user
Body (_Profile_) 


**Default** 

> Unexpected error
Body (_Error_Error_) 
```
{
  "code": 164,
  "message": "message",
  "fields": "fields"
}
```


[Back to API Reference](#api_reference)

## <a name="estimates"></a>![Endpoint Group: ](https://apidocs.io/img/class.png "Estimates") Estimates


### <a name="estimates_time"></a>![Endpoint: ](https://apidocs.io/img/method.png "EstimatesTime") `GET` /estimates/time

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates



#### Query Parameters
| Parameter | Type | Tags | Description | Example |
|-----------|------| ---- |-------------| ------- |
| start_latitude | `precision` |  ``` Required ```  | Latitude component of start location. | `164.352347175289` | 
| start_longitude | `precision` |  ``` Required ```  | Longitude component of start location. | `164.352347175289` | 
| customer_uuid | `uuid` |  ``` Optional ```  | Unique customer identifier to be used for experience customization. | `"0940a82f-981b-46a8-92ed-77b273e04f0e"` | 
| product_id | `string` |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. | `"product_id"` | 

#### Responses
**200** 

> An array of products
Body (_Product_) 
```
[
  {
    "product_id": "product_id",
    "description": "description",
    "display_name": "display_name",
    "capacity": "capacity",
    "image": "image"
  }
]
```


**Default** 

> Unexpected error
Body (_Error_Error_) 
```
{
  "code": 164,
  "message": "message",
  "fields": "fields"
}
```


### <a name="estimates_price"></a>![Endpoint: ](https://apidocs.io/img/method.png "EstimatesPrice") `GET` /estimates/price

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates



#### Query Parameters
| Parameter | Type | Tags | Description | Example |
|-----------|------| ---- |-------------| ------- |
| start_latitude | `precision` |  ``` Required ```  | Latitude component of start location. | `164.352347175289` | 
| start_longitude | `precision` |  ``` Required ```  | Longitude component of start location. | `164.352347175289` | 
| end_latitude | `precision` |  ``` Required ```  | Latitude component of end location. | `164.352347175289` | 
| end_longitude | `precision` |  ``` Required ```  | Longitude component of end location. | `164.352347175289` | 

#### Responses
**200** 

> An array of price estimates by product
Body (_PriceEstimate_) 
```
[
  {
    "product_id": "product_id",
    "currency_code": "currency_code",
    "display_name": "display_name",
    "estimate": "estimate",
    "low_estimate": 164.352347175289,
    "high_estimate": 164.352347175289,
    "surge_multiplier": 164.352347175289
  }
]
```


**Default** 

> Unexpected error
Body (_Error_Error_) 
```
{
  "code": 164,
  "message": "message",
  "fields": "fields"
}
```


[Back to API Reference](#api_reference)

## <a name="products"></a>![Endpoint Group: ](https://apidocs.io/img/class.png "Products") Products


### <a name="products"></a>![Endpoint: ](https://apidocs.io/img/method.png "Products") `GET` /products

> *Tags:*  ``` Skips Authentication ``` 

> Product Types



#### Query Parameters
| Parameter | Type | Tags | Description | Example |
|-----------|------| ---- |-------------| ------- |
| latitude | `precision` |  ``` Required ```  | Latitude component of location. | `12.5` | 
| longitude | `precision` |  ``` Required ```  | Longitude component of location. | `555.6` | 

#### Responses
**200** 

> An array of products
Body (_Product_) 
```
[
  {
    "product_id": "id",
    "description": "product description",
    "display_name": "XYZ",
    "capacity": "capacity",
    "image": ""
  }
]
```


**Default** 

> Unexpected error
Body (_Error_Error_) 
```
{
  "code": 164,
  "message": "message",
  "fields": "fields"
}
```


[Back to API Reference](#api_reference)

