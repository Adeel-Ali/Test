# Getting started

## How to Build

This client library is a Ruby gem which can be compiled and used in your Ruby and Ruby on Rails project. This library requires a few gems from the RubyGems repository.

1. Open the command line interface or the terminal and navigate to the folder containing the source code.
2. Run ``` gem build uber_api.gemspec ``` to build the gem.
3. Once built, the gem can be installed on the current work environment using ``` gem install uber_api-1.0.0.gem ```

![Building Gem](https://apidocs.io/illustration/ruby?step=buildSDK&workspaceFolder=Uber%20API-Ruby&workspaceName=Uber%20API-Ruby&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

## How to Use

The following section explains how to use the UberApi Ruby Gem in a new Rails project using RubyMine&trade;. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

### 1. Starting a new project

Close any existing projects in RubyMine&trade; by selecting ``` File -> Close Project ```. Next, click on ``` Create New Project ``` to create a new project from scratch.

![Create a new project in RubyMine](https://apidocs.io/illustration/ruby?step=createNewProject0&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

Next, provide ``` TestApp ``` as the project name, choose ``` Rails Application ``` as the project type, and click ``` OK ```.

![Create a new Rails Application in RubyMine - step 1](https://apidocs.io/illustration/ruby?step=createNewProject1&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

In the next dialog make sure that correct *Ruby SDK* is being used (minimum 2.0.0) and click ``` OK ```.

![Create a new Rails Application in RubyMine - step 2](https://apidocs.io/illustration/ruby?step=createNewProject2&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

This will create a new Rails Application project with an existing set of files and folder.

### 2. Add reference of the gem

In order to use the UberApi gem in the new project we must add a gem reference. Locate the ```Gemfile``` in the *Project Explorer* window under the ``` TestApp ``` project node. The file contains references to all gems being used in the project. Here, add the reference to the library gem by adding the following line: ``` gem 'uber_api', '~> 1.0.0' ```

![Add references of the Gemfile](https://apidocs.io/illustration/ruby?step=addReference&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

### 3. Adding a new Rails Controller

Once the ``` TestApp ``` project is created, a folder named ``` controllers ``` will be visible in the *Project Explorer* under the following path: ``` TestApp > app > controllers ```. Right click on this folder and select ``` New -> Run Rails Generator... ```.

![Run Rails Generator on Controllers Folder](https://apidocs.io/illustration/ruby?step=addCode0&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

Selecting the said option will popup a small window where the generator names are displayed. Here, select the ``` controller ``` template.

![Create a new Controller](https://apidocs.io/illustration/ruby?step=addCode1&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

Next, a popup window will ask you for a Controller name and included Actions. For controller name provide ``` Hello ``` and include an action named ``` Index ``` and click ``` OK ```.

![Add a new Controller](https://apidocs.io/illustration/ruby?step=addCode2&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

A new controller class anmed ``` HelloController ``` will be created in a file named ``` hello_controller.rb ``` containing a method named ``` Index ```. In this method, add code for initialization and a sample for its usage.

![Initialize the library](https://apidocs.io/illustration/ruby?step=addCode3&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0)

## How to Test

You can test the generated SDK and the server with automatically generated test
cases as follows:

  1. From terminal/cmd navigate to the root directory of the SDK.
  2. Invoke: `bundle exec rake`

## Initialization

### 

API client can be initialized as following.

```ruby

client = UberApi::UberApiClient.new
```

The added initlization code can be debugged by putting a breakpoint in the ``` Index ``` method and running the project in debug mode by selecting ``` Run -> Debug 'Development: TestApp' ```.

![Debug the TestApp](https://apidocs.io/illustration/ruby?step=addCode4&workspaceFolder=Uber%20API-Ruby&workspaceName=UberApi&projectName=uber_api&gemName=uber_api&gemVer=1.0.0&initLine=client%2520%253D%2520UberApiClient.new)

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [EstimatesController](#estimates_controller)
* [ProductsController](#products_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get singleton instance

The singleton instance of the ``` UserController ``` class can be accessed from the API Client.

```ruby
user = client.user
```

### <a name="get_history"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.get_history") get_history

> *Tags:*  ``` Skips Authentication ``` 

> User Activity


```ruby
def get_history(offset = nil, 
                    limit = nil); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |


#### Example Usage

```ruby
offset = 2
limit = 10

result = user.get_history(offset, limit)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_me"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.get_me") get_me

> *Tags:*  ``` Skips Authentication ``` 

> User Profile


```ruby
def get_me; end
```

#### Example Usage

```ruby

result = user.get_me()

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_controller"></a>![Class: ](https://apidocs.io/img/class.png ".EstimatesController") EstimatesController

### Get singleton instance

The singleton instance of the ``` EstimatesController ``` class can be accessed from the API Client.

```ruby
estimates = client.estimates
```

### <a name="get_estimates_time"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.get_estimates_time") get_estimates_time

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates


```ruby
def get_estimates_time(start_latitude, 
                           start_longitude, 
                           customer_uuid = nil, 
                           product_id = nil); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| start_latitude |  ``` Required ```  | Latitude component of start location. |
| start_longitude |  ``` Required ```  | Longitude component of start location. |
| customer_uuid |  ``` Optional ```  | Unique customer identifier to be used for experience customization. |
| product_id |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. |


#### Example Usage

```ruby
start_latitude = 15.036021180002
start_longitude = 15.036021180002
customer_uuid = UUID.new
product_id = 'product_id'

result = estimates.get_estimates_time(start_latitude, start_longitude, customer_uuid, product_id)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_estimates_price"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.get_estimates_price") get_estimates_price

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates


```ruby
def get_estimates_price(start_latitude, 
                            start_longitude, 
                            end_latitude, 
                            end_longitude); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| start_latitude |  ``` Required ```  | Latitude component of start location. |
| start_longitude |  ``` Required ```  | Longitude component of start location. |
| end_latitude |  ``` Required ```  | Latitude component of end location. |
| end_longitude |  ``` Required ```  | Longitude component of end location. |


#### Example Usage

```ruby
start_latitude = 15.036021180002
start_longitude = 15.036021180002
end_latitude = 15.036021180002
end_longitude = 15.036021180002

result = estimates.get_estimates_price(start_latitude, start_longitude, end_latitude, end_longitude)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="products_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ProductsController") ProductsController

### Get singleton instance

The singleton instance of the ``` ProductsController ``` class can be accessed from the API Client.

```ruby
products = client.products
```

### <a name="get_products"></a>![Method: ](https://apidocs.io/img/method.png ".ProductsController.get_products") get_products

> *Tags:*  ``` Skips Authentication ``` 

> Product Types


```ruby
def get_products(latitude, 
                     longitude); end
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |


#### Example Usage

```ruby
latitude = 12.5
longitude = 555.6

result = products.get_products(latitude, longitude)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)



