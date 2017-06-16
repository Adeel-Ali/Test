# Getting started

## How to Build

The generated code uses a few Gradle dependencies e.g., Jackson, Volley,
and Apache HttpClient. The reference to these dependencies is already
added in the build.gradle file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Android Studio click on ``` Open an Existing Android Project ```.

![Importing SDK into Android Studio - Step 1](https://apidocs.io/illustration/android?step=import1&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

* Browse to locate the folder containing the source code. Select the location of the UberAPILib gradle project and click ``` Ok ```.

![Importing SDK into Android Studio - Step 2](https://apidocs.io/illustration/android?step=import2&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

* Upon successful import, the project can be built by clicking on ``` Build > Make Project ``` or  pressing ``` Ctrl + F9 ```.

![Importing SDK into Android Studio - Step 3](https://apidocs.io/illustration/android?step=import3&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

## How to Use

The following section explains how to use the UberAPILib library in a new project.

### 1. Starting a new project 

For starting a new project, click on ``` Create New Android Studio Project ```.

![Add a new project in Android Studio - Step 1](https://apidocs.io/illustration/android?step=createNewProject0&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Here, configure the new project by adding the name, domain and location of the sample application followed by clicking ``` Next ```.

![Create a new Android Studio Project - Step 2](https://apidocs.io/illustration/android?step=createNewProject1&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Following this, select the ``` Phone and Tablet ```` option as shown in the illustration below and click ``` Next ```. 

![Create a new Android Studio Project - Step 3](https://apidocs.io/illustration/android?step=createNewProject2&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

In the following step, choose ``` Empty Activity ``` as the activity type and click ``` Next ```.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject3&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

In this step, provide an ``` Activity Name ``` and ``` Layout Name ``` and click ``` Finish ```.  This would take you to the newly created project.

![Create a new Android Studio Project - Step 4](https://apidocs.io/illustration/android?step=createNewProject4&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

### 2. Add reference of the library project

In order to add a dependency to this sample application, click on the android button shown in the project explorer on the left side as shown in the picture. Click on ``` Project ``` in the drop down that emerges.  

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/android?step=testProject0&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Right click the sample application in the project explorer and click on ``` New > Module ```  as shown in the picture.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/android?step=testProject1&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Choose ``` Import Gradle Project ``` and click ``` Next ```.

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/android?step=testProject2&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Click on ``` Finish ``` which would take you back to the sample application with the refernced SDK. 

![Adding dependency to the client library - Step 4](https://apidocs.io/illustration/android?step=testProject3&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

In the following step naigate to the ``` SampleApplication >  app > build.gradle ``` file and add the following line ```compile project(path: ':UberAPILib')``` to the dependencies section as shown in the illustration below.

![Adding dependency to the client library - Step 5](https://apidocs.io/illustration/android?step=testProject4&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Finally, press ``` Sync Now ``` in the warning visible as shown in the picture below.

![Adding dependency to the client library - Step 6](https://apidocs.io/illustration/android?step=testProject5&workspaceFolder=Uber%20API&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

### 3. Write sample code

Once the ``` SampleApplication ``` is created, a file named ``` SampleApplication > app > src > main > java > MainActivity ``` will be visible in the *Project Explorer* with an ``` onCreate ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Android Studio, for running the tests do the following:

1. Right click on *SampleApplication > UberAPILib > androidTest > java)* from the project explorer.
2. Select "Run All Tests" or use "Ctrl + Shift + F10" to run the Tests.

## Initialization

### 

API client can be initialized as following. The `appContext` being passed is the Android application [`Context`](https://developer.android.com/reference/android/content/Context.html).

```java

com.acme.corp.api.Configuration.initialize(appContext);
UberAPILibClient client = new UberAPILibClient();
```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [EstimatesController](#estimates_controller)
* [ProductsController](#products_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.acme.corp.api.controllers.UserController") UserController

### Get singleton instance

The singleton instance of the ``` UserController ``` class can be accessed from the API Client.

```java
UserController user = client.getUser();
```

### <a name="get_history_async"></a>![Method: ](https://apidocs.io/img/method.png "com.acme.corp.api.controllers.UserController.getHistoryAsync") getHistoryAsync

> *Tags:*  ``` Skips Authentication ``` 

> User Activity


```java
void getHistoryAsync(
        final Integer offset,
        final Integer limit,
        final APICallBack<ActivitiesModel> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |


#### Example Usage

```java
Integer offset = 2;
Integer limit = 10;
// Invoking the API call with sample inputs
user.getHistoryAsync(offset, limit, new APICallBack<ActivitiesModel>() {
    public void onSuccess(HttpContext context, ActivitiesModel response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_me_async"></a>![Method: ](https://apidocs.io/img/method.png "com.acme.corp.api.controllers.UserController.getMeAsync") getMeAsync

> *Tags:*  ``` Skips Authentication ``` 

> User Profile


```java
void getMeAsync(final APICallBack<ProfileModel> callBack)
```

#### Example Usage

```java
// Invoking the API call with sample inputs
user.getMeAsync(new APICallBack<ProfileModel>() {
    public void onSuccess(HttpContext context, ProfileModel response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.acme.corp.api.controllers.EstimatesController") EstimatesController

### Get singleton instance

The singleton instance of the ``` EstimatesController ``` class can be accessed from the API Client.

```java
EstimatesController estimates = client.getEstimates();
```

### <a name="get_estimates_time_async"></a>![Method: ](https://apidocs.io/img/method.png "com.acme.corp.api.controllers.EstimatesController.getEstimatesTimeAsync") getEstimatesTimeAsync

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates


```java
void getEstimatesTimeAsync(
        final double startLatitude,
        final double startLongitude,
        final UUID customerUuid,
        final String productId,
        final APICallBack<List<ProductModel>> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| customerUuid |  ``` Optional ```  | Unique customer identifier to be used for experience customization. |
| productId |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. |


#### Example Usage

```java
double startLatitude = 156.30341173676;
double startLongitude = 156.30341173676;
UUID customerUuid = UUID.randomUUID();
String productId = "product_id";
// Invoking the API call with sample inputs
estimates.getEstimatesTimeAsync(startLatitude, startLongitude, customerUuid, productId, new APICallBack<List<ProductModel>>() {
    public void onSuccess(HttpContext context, List<ProductModel> response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_estimates_price_async"></a>![Method: ](https://apidocs.io/img/method.png "com.acme.corp.api.controllers.EstimatesController.getEstimatesPriceAsync") getEstimatesPriceAsync

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates


```java
void getEstimatesPriceAsync(
        final double startLatitude,
        final double startLongitude,
        final double endLatitude,
        final double endLongitude,
        final APICallBack<List<PriceEstimateModel>> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |


#### Example Usage

```java
double startLatitude = 156.30341173676;
double startLongitude = 156.30341173676;
double endLatitude = 156.30341173676;
double endLongitude = 156.30341173676;
// Invoking the API call with sample inputs
estimates.getEstimatesPriceAsync(startLatitude, startLongitude, endLatitude, endLongitude, new APICallBack<List<PriceEstimateModel>>() {
    public void onSuccess(HttpContext context, List<PriceEstimateModel> response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="products_controller"></a>![Class: ](https://apidocs.io/img/class.png "com.acme.corp.api.controllers.ProductsController") ProductsController

### Get singleton instance

The singleton instance of the ``` ProductsController ``` class can be accessed from the API Client.

```java
ProductsController products = client.getProducts();
```

### <a name="get_products_async"></a>![Method: ](https://apidocs.io/img/method.png "com.acme.corp.api.controllers.ProductsController.getProductsAsync") getProductsAsync

> *Tags:*  ``` Skips Authentication ``` 

> Product Types


```java
void getProductsAsync(
        final double latitude,
        final double longitude,
        final APICallBack<List<ProductModel>> callBack)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |


#### Example Usage

```java
double latitude = 12.5;
double longitude = 555.6;
// Invoking the API call with sample inputs
products.getProductsAsync(latitude, longitude, new APICallBack<List<ProductModel>>() {
    public void onSuccess(HttpContext context, List<ProductModel> response) {
        // TODO success callback handler
    }
    public void onFailure(HttpContext context, Throwable error) {
        // TODO failure callback handler
    }
});

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)



