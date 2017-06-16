# Getting started

## How to Build

The generated SDK relies on [Node Package Manager](https://www.npmjs.com/) (NPM) being available to resolve dependencies. If you don't already have NPM installed, please go ahead and follow instructions to install NPM from [here](https://nodejs.org/en/download/).
The SDK also requires Node to be installed. If Node isn't already installed, please install it from [here](https://nodejs.org/en/download/)
> NPM is installed by default when Node is installed

To check if node and npm have been successfully installed, write the following commands in command prompt:
* `node --version`
* `npm -version` 
![Version Check](https://apidocs.io/illustration/nodejs?step=versionCheck&workspaceFolder=Uber%20API-Node)  

Now use npm to resolve all dependencies by running the following command in the root directory (of the SDK folder):
* `npm install`
![Resolve Dependencies](https://apidocs.io/illustration/nodejs?step=resolveDependency1&workspaceFolder=Uber%20API-Node)
![Resolve Dependencies](https://apidocs.io/illustration/nodejs?step=resolveDependency2)

This will install all dependencies in the `node_modules` folder. 

Once dependencies are resolved, you will need to move the folder `UberAPILib ` in to your `node_modules` folder.

## How to Use

The following section explains how to use the library in a new project.

### 1. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`
![Open Folder](https://apidocs.io/illustration/nodejs?step=openFolder)

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.
![Open Project](https://apidocs.io/illustration/nodejs?step=openProject&workspaceFolder=Uber%20API-Node)


### 2. Creating a Test File
Now right click on the folder name and select the `New File` option to create a new test file.    Save it as `index.js` Now import the generated NodeJS library using the following lines of code:
```JavaScript
var lib = require('lib');
```
Save changes.

![Create new file](https://apidocs.io/illustration/nodejs?step=createNewFile&workspaceFolder=Uber%20API-Node)
![Save new file](https://apidocs.io/illustration/nodejs?step=saveNewFile&workspaceFolder=Uber%20API-Node)

### 3. Running The Test File
To run the `index.js` file, open up the command prompt and navigate to the Path where the SDK folder resides. Type the following command to run the file:  
`node index.js`
![Run file](https://apidocs.io/illustration/nodejs?step=runProject&workspaceFolder=Uber%20API-Node)


## How to Test

These tests use Mocha framework for testing, coupled with Chai for assertions. These dependencies need to be installed for tests to run.
Tests can be run in a number of ways:

### Method 1 
###### (Run all tests)

1. Navigate to the root directory of the SDK folder from command prompt.
2. Type `mocha --recursive` to run all the tests.

### Method 2
###### (Run all tests)

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha *` to run all the tests.

### Method 3
###### (Run specific controller's tests)

1. Navigate to the `../test/Controllers/` directory from command prompt.
2. Type `mocha  Uber APIController`  to run all the tests in that controller file.

> To increase mocha's default timeout, you can change the `TEST_TIMEOUT` parameter's value in `TestBootstrap.js`.  

![Run Tests](https://apidocs.io/illustration/nodejs?step=runTests&controllerName=Uber%20APIController)

## Initialization

### 

API client can be initialized as following:

```JavaScript
var lib = require('lib');


```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [EstimatesController](#estimates_controller)
* [ProductsController](#products_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get singleton instance

The singleton instance of the ``` UserController ``` class can be accessed from the API Client.

```javascript
var controller = lib.UserController;
```

### <a name="get_history"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getHistory") getHistory

> *Tags:*  ``` Skips Authentication ``` 

> User Activity


```javascript
function getHistory(offset, limit, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |



#### Example Usage

```javascript

    var offset = 2;
    var limit = 10;

    controller.getHistory(offset, limit, function(error, response, context) {

    
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




### <a name="get_me"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getMe") getMe

> *Tags:*  ``` Skips Authentication ``` 

> User Profile


```javascript
function getMe(callback)
```

#### Example Usage

```javascript


    controller.getMe(function(error, response, context) {

    
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_controller"></a>![Class: ](https://apidocs.io/img/class.png ".EstimatesController") EstimatesController

### Get singleton instance

The singleton instance of the ``` EstimatesController ``` class can be accessed from the API Client.

```javascript
var controller = lib.EstimatesController;
```

### <a name="get_estimates_time"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.getEstimatesTime") getEstimatesTime

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates


```javascript
function getEstimatesTime(startLatitude, startLongitude, customerUuid, productId, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| customerUuid |  ``` Optional ```  | Unique customer identifier to be used for experience customization. |
| productId |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. |



#### Example Usage

```javascript

    var startLatitude = 37.2733487315818;
    var startLongitude = 37.2733487315818;
    var customerUuid = uniqid();
    var productId = product_id;

    controller.getEstimatesTime(startLatitude, startLongitude, customerUuid, productId, function(error, response, context) {

    
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




### <a name="get_estimates_price"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.getEstimatesPrice") getEstimatesPrice

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates


```javascript
function getEstimatesPrice(startLatitude, startLongitude, endLatitude, endLongitude, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |



#### Example Usage

```javascript

    var startLatitude = 37.2733487315818;
    var startLongitude = 37.2733487315818;
    var endLatitude = 37.2733487315818;
    var endLongitude = 37.2733487315818;

    controller.getEstimatesPrice(startLatitude, startLongitude, endLatitude, endLongitude, function(error, response, context) {

    
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)

## <a name="products_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ProductsController") ProductsController

### Get singleton instance

The singleton instance of the ``` ProductsController ``` class can be accessed from the API Client.

```javascript
var controller = lib.ProductsController;
```

### <a name="get_products"></a>![Method: ](https://apidocs.io/img/method.png ".ProductsController.getProducts") getProducts

> *Tags:*  ``` Skips Authentication ``` 

> Product Types


```javascript
function getProducts(latitude, longitude, callback)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |



#### Example Usage

```javascript

    var latitude = 12.5;
    var longitude = 555.6;

    controller.getProducts(latitude, longitude, function(error, response, context) {

    
	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)



