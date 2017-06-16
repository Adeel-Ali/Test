# Getting started

## How to Build

The generated SDK requires AngularJS framework to work. If you do not already have angular downloaded, please go ahead and do it from [here](https://angularjs.org/).
If any of your models have `Date` or `Datetime` type fields or your endpoints have `Date`/`Datetime` type response, you will need to download and link [angular-moment](https://cdnjs.cloudflare.com/ajax/libs/angular-moment/1.0.1/angular-moment.min.js) and [moment.js](https://cdnjs.cloudflare.com/ajax/libs/moment.js/2.17.1/moment.min.js) with your project.

## How to Use

The following section describes how to use the generated SDK in an existing/new project.

### 1. Configure Angular and Generated SDK
Perform the following steps to configure angular and the SDK:
+ Make a `scripts` folder inside the root folder of the project. If you already have a `scripts` folder, skip to the next step.
+ Move the `angular.min.js` file inside the scripts folder. 
+ Move the `uberapilib` folder inside the scripts folder.
+ If any of the Custom Types in your API have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will need to download angular-moment and moment.js. Move these 2 files into the `scripts` folder as well.

![folder-structure-image](https://apidocs.io/illustration/angularjs?step=folderStructure&workspaceFolder=Uber%20API-Angular&projectName=UberAPILib)

### 2. Open Project Folder
Open an IDE/Text Editor for JavaScript like Sublime Text. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.  
Click on `File` and select `Open Folder`

Select the folder of your SDK and click on `Select Folder` to open it up in Sublime Text. The folder will become visible in the bar on the left.

![open-folder-image](https://apidocs.io/illustration/angularjs?step=openFolder&workspaceFolder=Uber%20API-Angular)

### 3. Create an Angular Application
Since Angular JS is used for client-side web development, in order to use the generated library, you will have to develop an application first.
If you already have an angular application, [skip to Step 6](#6-include-sdk-references-in-html-file). Otherwise, follow these steps to create one:

+ In the IDE, click on `File` and choose `New File` to create a new file.
+ Add the following starting code in the file:
```js
    var app = angular.module('myApp', []);
    app.controller('testController', function($scope) 
    {

    });
```
+ Save it with the name `app.js` in the `scripts` folder.


### 4. Create HTML File
Skip to the next step if you are working with an existing project and already have an html file. Otherwise follow the steps to create one:
+ Inside the IDE, right click on the project folder name and select the `New File` option to create a new test file.
+ Save it with an appropriate name such as `index.html` in the root of your project folder.
`index.html` should look like this:
```html
	<!DOCTYPE html>
	<html>
	<head>
		<title>Angular Project</title>
		<script></script>
	</head>

	<body>
	</body>

	</html>
```

![initial-html-code-image](https://apidocs.io/illustration/angularjs?step=initialCode&workspaceFolder=Uber%20API-Angular)

### 5. Including links to Angular in HTML file
Your HTML file needs to have a link to `angular.min.js` file to use Angular-JS. Add the link using `script` tags inside the `head` section of `index.html` like:
```html
	<script src="scripts/angular.min.js" ></script>
```
If any of the Custom Types that you have defined have `Date`/`Datetime` type fields or any endpoint has `Date`/`Datetime` response, you will also need to link to angular-moment and moment.js like:
```html
	<script src="scripts/angular.min.js" ></script>
	<script src="scripts/moment.min.js" ></script>
	<script src="scripts/angular-moment.min.js" ></script>
```

### 6. Include SDK references in HTML file
Import the reference to the generated SDK files inside your html file like:
```html
	<head>
		...
		<!-- Helper files -->
		<script src="scripts/uberapilib/Module.js"></script>
		<script src="scripts/uberapilib/Configuration.js"></script>
		<script src="scripts/uberapilib/ModelFactory.js"></script>
		<script src="scripts/uberapilib/ObjectMapper.js"></script>
		<script src="scripts/uberapilib/APIHelper.js"></script>
		<script src="scripts/uberapilib/Http/Client/HttpContext.js"></script>
		<script src="scripts/uberapilib/Http/Client/RequestClient.js"></script>
		<script src="scripts/uberapilib/Http/Request/HttpRequest.js"></script>
		<script src="scripts/uberapilib/Http/Response/HttpResponse.js"></script>

		<!-- API Controllers -->
        <script src="scripts/uberapilib/Controllers/BaseController.js"></script>
        <script src="scripts/uberapilib/Controllers/UserController.js"></script>
        <script src="scripts/uberapilib/Controllers/EstimatesController.js"></script>
        <script src="scripts/uberapilib/Controllers/ProductsController.js"></script>


		<!-- Models -->
        <script src="scripts/uberapilib/Models/BaseModel.js"></script>
        <script src="scripts/uberapilib/Models/ActivityModel.js"></script>
        <script src="scripts/uberapilib/Models/TemplateParamEnum.js"></script>
        <script src="scripts/uberapilib/Models/ProductModel.js"></script>
        <script src="scripts/uberapilib/Models/PriceEstimateModel.js"></script>
        <script src="scripts/uberapilib/Models/ProfileModel.js"></script>
        <script src="scripts/uberapilib/Models/ActivitiesModel.js"></script>

		...
	</head>
```
> The `Module.js` file should be imported before the other files. After `Module.js`, `Configuration.js` should be imported.
> The `ModelFactory.js` file is needed by `ObjectMapper.js` file. The `ObjectMapper` in turn, is needed by `BaseController.js`.

### 7. Including link to `app.js` in HTML file
Link your `app.js` file to your `index.html` file like:
```html
	<head>
		...
		<script src="scripts/app.js"></script>
	</head>
```
> The link to app.js needs to be included at the very end of the head tag, after the SDK references have been added

### 8. Initializing the Angular App
You need to initialize your app and the controller associated with your view inside your `index.html` file. Do so like:
+ Add ng-app directive to initialize your app inside the `body` tag.
```html
	<body ng-app="myApp">
```
+ Add ng-controller directive to initialize your controller and bind it with your view (`index.html` file).
```html
	...
	<body ng-app="myApp">
		<div ng-controller="testController">
			...
		</div>
		...
	</body>
	...
```

### 9. Consuming the SDK 
In order to use the generated SDK's modules, controllers and factories, the project needs to be added as a dependency in your angular app's module. This will be done inside the `app.js` file.
Add the dependency like this:

```js
    var app = angular.module('myApp', ['UberAPILib']);
```
At this point, the SDK has been successfully included in your project. Further steps include using a service/factory from the generated SDK. To see working example of this, please head on [over here](#list-of-controllers) and choose any class to see its functions and example usage.  

### 10. Running The App
To run the app, simply open up the `index.html` file in a browser.

![app-running](https://apidocs.io/illustration/angularjs?step=appRunning)

## Initialization

### 

The Angular App can be initialized as following:
```html
<body ng-app="myApp">
    <div ng-controller="testController">
        ...
    </div>
    ...
</body>
```
> The initialization code will be added inside the `index.html` file (which is the view of the app you have created). More detail about this can be found in the [`How to Use`](#how-to-use) section

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [EstimatesController](#estimates_controller)
* [ProductsController](#products_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get singleton instance

The singleton instance of the ``` UserController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, UserController, ActivitiesModel, ProfileModel){
	});
```

### <a name="get_history"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.getHistory") getHistory

> *Tags:*  ``` Skips Authentication ``` 

> User Activity


```javascript
function getHistory(offset, limit)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |



#### Example Usage

```javascript


	app.controller("testController", function($scope, UserController, ActivitiesModel){
        var offset = 2;
        var limit = 10;


		var result = UserController.getHistory(offset, limit);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

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
function getMe()
```

#### Example Usage

```javascript


	app.controller("testController", function($scope, UserController, ProfileModel){


		var result = UserController.getMe();
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_controller"></a>![Class: ](https://apidocs.io/img/class.png ".EstimatesController") EstimatesController

### Get singleton instance

The singleton instance of the ``` EstimatesController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, EstimatesController, ProductModel, PriceEstimateModel){
	});
```

### <a name="get_estimates_time"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.getEstimatesTime") getEstimatesTime

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates


```javascript
function getEstimatesTime(startLatitude, startLongitude, customerUuid, productId)
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


	app.controller("testController", function($scope, EstimatesController, ProductModel){
        var startLatitude = 78.9965219581484;
        var startLongitude = 78.9965219581484;
        var customerUuid = uniqid();
        var productId = product_id;


		var result = EstimatesController.getEstimatesTime(startLatitude, startLongitude, customerUuid, productId);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

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
function getEstimatesPrice(startLatitude, startLongitude, endLatitude, endLongitude)
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


	app.controller("testController", function($scope, EstimatesController, PriceEstimateModel){
        var startLatitude = 78.9965219581484;
        var startLongitude = 78.9965219581484;
        var endLatitude = 78.9965219581484;
        var endLongitude = 78.9965219581484;


		var result = EstimatesController.getEstimatesPrice(startLatitude, startLongitude, endLatitude, endLongitude);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)

## <a name="products_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ProductsController") ProductsController

### Get singleton instance

The singleton instance of the ``` ProductsController ``` class can be accessed via Dependency Injection.

```js
	app.controller("testController", function($scope, ProductsController, ProductModel){
	});
```

### <a name="get_products"></a>![Method: ](https://apidocs.io/img/method.png ".ProductsController.getProducts") getProducts

> *Tags:*  ``` Skips Authentication ``` 

> Product Types


```javascript
function getProducts(latitude, longitude)
```
#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |



#### Example Usage

```javascript


	app.controller("testController", function($scope, ProductsController, ProductModel){
        var latitude = 12.5;
        var longitude = 555.6;


		var result = ProductsController.getProducts(latitude, longitude);
        //Function call returns a promise
        result.then(function(success){
			//success case
			//getting context of response
			console.log(success.getContext());
		},function(err){
			//failure case
		});

	});
```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)



