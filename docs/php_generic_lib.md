# Getting started

## How to Build

The generated code has dependencies over external libraries like UniRest. These dependencies are defined in the ```composer.json``` file that comes with the SDK. 
To resolve these dependencies, we use the Composer package manager which requires PHP greater than 5.3.2 installed in your system. 
Visit [https://getcomposer.org/download/](https://getcomposer.org/download/) to download the installer file for Composer and run it in your system. 
Open command prompt and type ```composer --version```. This should display the current version of the Composer installed if the installation was successful.

* Using command line, navigate to the directory containing the generated files (including ```composer.json```) for the SDK. 
* Run the command ```composer install```. This should install all the required dependencies and create the ```vendor``` directory in your project directory.

![Building SDK - Step 1](https://apidocs.io/illustration/php?step=installDependencies&workspaceFolder=Uber%20API-PHP)

### [For Windows Users Only] Configuring CURL Certificate Path in php.ini

CURL used to include a list of accepted CAs, but no longer bundles ANY CA certs. So by default it will reject all SSL certificates as unverifiable. You will have to get your CA's cert and point curl at it. The steps are as follows:

1. Download the certificate bundle (.pem file) from [https://curl.haxx.se/docs/caextract.html](https://curl.haxx.se/docs/caextract.html) on to your system.
2. Add curl.cainfo = "PATH_TO/cacert.pem" to your php.ini file located in your php installation. “PATH_TO” must be an absolute path containing the .pem file.

```ini
[curl]
; A default value for the CURLOPT_CAINFO option. This is required to be an
; absolute path.
;curl.cainfo =
```

## How to Use

The following section explains how to use the UberAPILib library in a new project.

### 1. Open Project in an IDE

Open an IDE for PHP like PhpStorm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=openIDE&workspaceFolder=Uber%20API-PHP)

Click on ```Open``` in PhpStorm to browse to your generated SDK directory and then click ```OK```.

![Open project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=openProject0&workspaceFolder=Uber%20API-PHP)     

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PHPStorm - Step 1](https://apidocs.io/illustration/php?step=createDirectory&workspaceFolder=Uber%20API-PHP)

Name the directory as "test"

![Add a new project in PHPStorm - Step 2](https://apidocs.io/illustration/php?step=nameDirectory&workspaceFolder=Uber%20API-PHP)
   
Add a PHP file to this project

![Add a new project in PHPStorm - Step 3](https://apidocs.io/illustration/php?step=createFile&workspaceFolder=Uber%20API-PHP)

Name it "testSDK"

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=nameFile&workspaceFolder=Uber%20API-PHP)

Depending on your project setup, you might need to include composer's autoloader in your PHP code to enable auto loading of classes.

```PHP
require_once "../vendor/autoload.php";
```

It is important that the path inside require_once correctly points to the file ```autoload.php``` inside the vendor directory created during dependency installations.

![Add a new project in PHPStorm - Step 4](https://apidocs.io/illustration/php?step=projectFiles&workspaceFolder=Uber%20API-PHP)

After this you can add code to initialize the client library and acquire the instance of a Controller class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

### 3. Run the Test Project

To run your project you must set the Interpreter for your project. Interpreter is the PHP engine installed on your computer.

Open ```Settings``` from ```File``` menu.

![Run Test Project - Step 1](https://apidocs.io/illustration/php?step=openSettings&workspaceFolder=Uber%20API-PHP)

Select ```PHP``` from within ```Languages & Frameworks```

![Run Test Project - Step 2](https://apidocs.io/illustration/php?step=setInterpreter0&workspaceFolder=Uber%20API-PHP)

Browse for Interpreters near the ```Interpreter``` option and choose your interpreter.

![Run Test Project - Step 3](https://apidocs.io/illustration/php?step=setInterpreter1&workspaceFolder=Uber%20API-PHP)

Once the interpreter is selected, click ```OK```

![Run Test Project - Step 4](https://apidocs.io/illustration/php?step=setInterpreter2&workspaceFolder=Uber%20API-PHP)

To run your project, right click on your PHP file inside your Test project and click on ```Run```

![Run Test Project - Step 5](https://apidocs.io/illustration/php?step=runProject&workspaceFolder=Uber%20API-PHP)

## How to Test

Unit tests in this SDK can be run using PHPUnit. 

1. First install the dependencies using composer including the `require-dev` dependencies.
2. Run `vendor\bin\phpunit --verbose` from commandline to execute tests. If you have 
   installed PHPUnit globally, run tests using `phpunit --verbose` instead.

You can change the PHPUnit test configuration in the `phpunit.xml` file.

## Initialization

### 

API client can be initialized as following.

```php

$client = new UberAPILib\UberAPILibClient();
```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [EstimatesController](#estimates_controller)
* [ProductsController](#products_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get singleton instance

The singleton instance of the ``` UserController ``` class can be accessed from the API Client.

```php
$user = $client->getUser();
```

### <a name="get_history"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getHistory") getHistory

> *Tags:*  ``` Skips Authentication ``` 

> User Activity


```php
function getHistory(
        $offset = null,
        $limit = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |



#### Example Usage

```php
$offset = 2;
$limit = 10;

$result = $user->getHistory($offset, $limit);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_me"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getMe") getMe

> *Tags:*  ``` Skips Authentication ``` 

> User Profile


```php
function getMe()
```

#### Example Usage

```php

$result = $user->getMe();

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_controller"></a>![Class: ](https://apidocs.io/img/class.png ".EstimatesController") EstimatesController

### Get singleton instance

The singleton instance of the ``` EstimatesController ``` class can be accessed from the API Client.

```php
$estimates = $client->getEstimates();
```

### <a name="get_estimates_time"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.getEstimatesTime") getEstimatesTime

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates


```php
function getEstimatesTime(
        $startLatitude,
        $startLongitude,
        $customerUuid = null,
        $productId = null)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| customerUuid |  ``` Optional ```  | Unique customer identifier to be used for experience customization. |
| productId |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. |



#### Example Usage

```php
$startLatitude = 114.580238510193;
$startLongitude = 114.580238510193;
$customerUuid = uniqid();
$productId = 'product_id';

$result = $estimates->getEstimatesTime($startLatitude, $startLongitude, $customerUuid, $productId);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_estimates_price"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.getEstimatesPrice") getEstimatesPrice

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates


```php
function getEstimatesPrice(
        $startLatitude,
        $startLongitude,
        $endLatitude,
        $endLongitude)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |



#### Example Usage

```php
$startLatitude = 114.580238510193;
$startLongitude = 114.580238510193;
$endLatitude = 114.580238510193;
$endLongitude = 114.580238510193;

$result = $estimates->getEstimatesPrice($startLatitude, $startLongitude, $endLatitude, $endLongitude);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="products_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ProductsController") ProductsController

### Get singleton instance

The singleton instance of the ``` ProductsController ``` class can be accessed from the API Client.

```php
$products = $client->getProducts();
```

### <a name="get_products"></a>![Method: ](https://apidocs.io/img/method.png ".ProductsController.getProducts") getProducts

> *Tags:*  ``` Skips Authentication ``` 

> Product Types


```php
function getProducts(
        $latitude,
        $longitude)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |



#### Example Usage

```php
$latitude = 12.5;
$longitude = 555.6;

$result = $products->getProducts($latitude, $longitude);

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)



