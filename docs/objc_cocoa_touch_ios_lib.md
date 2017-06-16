# Getting started

## How to Build


The generated code has dependencies over external libraries like UniRest. These dependencies are defined in the ```PodFile``` file that comes with the SDK. 
To resolve these dependencies, we use the Cocoapods package manager.
Visit https://guides.cocoapods.org/using/getting-started.html to setup Cocoapods on your system.
Open command prompt and type ```pod --version```. This should display the current version of Cocoapods installed if the installation was successful.

Using command line, navigate to the directory containing the generated files (including ```PodFile```) for the SDK. 
Run the command ```pod install```. This should install all the required dependencies and create the ```pods``` directory in your project directory.

![Installing dependencies using Cocoapods](https://apidocs.io/illustration/objc?step=AddDependencies&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)

Open the project workspace using the (UberAPI.xcworkspace) file. Invoke the build process using `Command(⌘)+B` shortcut key or using the `Build` menu as shown below.

![Building SDK using Xcode](https://apidocs.io/illustration/objc?step=BuildSDK&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)


## How to Use

The generated code is a Cocoa Touch Static Library which can be used in any iOS project. The support for these generated libraries go all the way back to iOS 6.

The following section explains how to use the UberAPI library in a new iOS project.     
### 1. Starting a new project
To start a new project, left-click on the ```Create a new Xcode project```.
![Create Test Project - Step 1](https://apidocs.io/illustration/objc?step=Test1&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)

Next, choose **Single View Application** and click ```Next```.
![Create Test Project - Step 2](https://apidocs.io/illustration/objc?step=Test2&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)

Provide **Test-Project** as the product name click ```Next```.
![Create Test Project - Step 3](https://apidocs.io/illustration/objc?step=Test3&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)

Choose the desired location of your project folder and click ```Create```.
![Create Test Project - Step 4](https://apidocs.io/illustration/objc?step=Test4&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)

### 2. Adding the static library dependency
To add this dependency open a terminal and navigate to your project folder. Next, input ```pod init``` and press enter.
![Add dependency - Step 1](https://apidocs.io/illustration/objc?step=Add0&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)

Next, open the newly created ```PodFile``` in your favourite text editor. Add the following line : pod 'UberAPI', :path => 'Vendor/UberAPI'
![Add dependency - Step 2](https://apidocs.io/illustration/objc?step=Add1&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)

Execute `pod install` from terminal to install the dependecy in your project. This would add the dependency to the newly created test project.
![Add dependency - Step 3](https://apidocs.io/illustration/objc?step=Add2&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)


## How to Test

Unit tests in this SDK can be run using Xcode. 

First build the SDK as shown in the steps above and naivgate to the project directory and open the UberAPI.xcworkspace file.

Go to the test explorer in Xcode as shown in the picture below and click on `run tests` from the menu. 
![Run tests](https://apidocs.io/illustration/objc?step=RunTests&workspaceFolder=Uber%20API-ObjC&workspaceName=UberAPI&projectName=UberAPI&rootNamespace=UberAPI)


## Initialization

### 

Configuration variables can be set as following.
```Objc

```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [EstimatesController](#estimates_controller)
* [ProductsController](#products_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get singleton instance
```objc
User* user = [[User alloc]init] ;
```

### <a name="get_history_async_with_offset"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getHistoryAsyncWithOffset") getHistoryAsyncWithOffset

> *Tags:*  ``` Skips Authentication ``` 

> User Activity


```objc
function getHistoryAsyncWithOffset:(NSNumber*) offset
                limit:(NSNumber*) limit
                completionBlock:(CompletedGetHistory) onCompleted(offset limit : limit)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |





#### Example Usage

```objc
    // Parameters for the API call
    NSNumber* offset = [NSNumber numberWithInteger:[@"2" integerValue]];
    NSNumber* limit = [NSNumber numberWithInteger:[@"10" integerValue]];

    [self.user getHistoryAsyncWithOffset: offset limit : limit  completionBlock:^(BOOL success, HttpContext* context, ActivitiesModel* response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_me_with_completion_block"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getMeWithCompletionBlock") getMeWithCompletionBlock

> *Tags:*  ``` Skips Authentication ``` 

> User Profile


```objc
function getMeWithCompletionBlock:(CompletedGetMe) onCompleted()
```



#### Example Usage

```objc

    [self.user getMeWithCompletionBlock:  ^(BOOL success, HttpContext* context, ProfileModel* response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_controller"></a>![Class: ](https://apidocs.io/img/class.png ".EstimatesController") EstimatesController

### Get singleton instance
```objc
Estimates* estimates = [[Estimates alloc]init] ;
```

### <a name="get_estimates_time_async_with_start_latitude"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.getEstimatesTimeAsyncWithStartLatitude") getEstimatesTimeAsyncWithStartLatitude

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates


```objc
function getEstimatesTimeAsyncWithStartLatitude:(double) startLatitude
                startLongitude:(double) startLongitude
                customerUuid:(NSUUID*) customerUuid
                productId:(NSString*) productId
                completionBlock:(CompletedGetEstimatesTime) onCompleted(startLatitude startLongitude : startLongitude customerUuid : customerUuid productId : productId)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| customerUuid |  ``` Optional ```  | Unique customer identifier to be used for experience customization. |
| productId |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. |





#### Example Usage

```objc
    // Parameters for the API call
    double startLatitude = 242.501240066486;
    double startLongitude = 242.501240066486;
    NSUUID* customerUuid = 123456789;
    NSString* productId = @"product_id";

    [self.estimates getEstimatesTimeAsyncWithStartLatitude: startLatitude startLongitude : startLongitude customerUuid : customerUuid productId : productId  completionBlock:^(BOOL success, HttpContext* context, NSArray<ProductModel> * response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_estimates_price_async_with_start_latitude"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.getEstimatesPriceAsyncWithStartLatitude") getEstimatesPriceAsyncWithStartLatitude

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates


```objc
function getEstimatesPriceAsyncWithStartLatitude:(double) startLatitude
                startLongitude:(double) startLongitude
                endLatitude:(double) endLatitude
                endLongitude:(double) endLongitude
                completionBlock:(CompletedGetEstimatesPrice) onCompleted(startLatitude startLongitude : startLongitude endLatitude : endLatitude endLongitude : endLongitude)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |





#### Example Usage

```objc
    // Parameters for the API call
    double startLatitude = 242.501240066486;
    double startLongitude = 242.501240066486;
    double endLatitude = 242.501240066486;
    double endLongitude = 242.501240066486;

    [self.estimates getEstimatesPriceAsyncWithStartLatitude: startLatitude startLongitude : startLongitude endLatitude : endLatitude endLongitude : endLongitude  completionBlock:^(BOOL success, HttpContext* context, NSArray<PriceEstimateModel> * response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="products_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ProductsController") ProductsController

### Get singleton instance
```objc
Products* products = [[Products alloc]init] ;
```

### <a name="get_products_async_with_latitude"></a>![Method: ](https://apidocs.io/img/method.png ".ProductsController.getProductsAsyncWithLatitude") getProductsAsyncWithLatitude

> *Tags:*  ``` Skips Authentication ``` 

> Product Types


```objc
function getProductsAsyncWithLatitude:(double) latitude
                longitude:(double) longitude
                completionBlock:(CompletedGetProducts) onCompleted(latitude longitude : longitude)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |





#### Example Usage

```objc
    // Parameters for the API call
    double latitude = [@"12.5" doubleValue];
    double longitude = [@"555.6" doubleValue];

    [self.products getProductsAsyncWithLatitude: latitude longitude : longitude  completionBlock:^(BOOL success, HttpContext* context, NSArray<ProductModel> * response, NSError* error) { 
       //Add code here
    }];
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)



