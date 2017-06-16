# Getting started

## How to Build

The generated code uses a few Maven dependencies e.g., Jackson, UniRest,
and Apache HttpClient. The reference to these dependencies is already
added in the pom.xml file will be installed automatically. Therefore,
you will need internet access for a successful build.

* In order to open the client library in Eclipse click on ``` File -> Import ```.

![Importing SDK into Eclipse - Step 1](https://apidocs.io/illustration/java?step=import0&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

* In the import dialog, select ``` Existing Java Project ``` and click ``` Next ```.

![Importing SDK into Eclipse - Step 2](https://apidocs.io/illustration/java?step=import1&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

* Browse to locate the folder containing the source code. Select the detected location of the project and click ``` Finish ```.

![Importing SDK into Eclipse - Step 3](https://apidocs.io/illustration/java?step=import2&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

* Upon successful import, the project will be automatically built by Eclipse after automatically resolving the dependencies.

![Importing SDK into Eclipse - Step 4](https://apidocs.io/illustration/java?step=import3&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

## How to Use

The following section explains how to use the UberAPILib library in a new console project.

### 1. Starting a new project

For starting a new project, click the menu command ``` File > New > Project ```.

![Add a new project in Eclipse](https://apidocs.io/illustration/java?step=createNewProject0&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Next, choose ``` Maven > Maven Project ```and click ``` Next ```.

![Create a new Maven Project - Step 1](https://apidocs.io/illustration/java?step=createNewProject1&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Here, make sure to use the current workspace by choosing ``` Use default Workspace location ```, as shown in the picture below and click ``` Next ```.

![Create a new Maven Project - Step 2](https://apidocs.io/illustration/java?step=createNewProject2&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Following this, select the *quick start* project type to create a simple project with an existing class and a ``` main ``` method. To do this, choose ``` maven-archetype-quickstart ``` item from the list and click ``` Next ```.

![Create a new Maven Project - Step 3](https://apidocs.io/illustration/java?step=createNewProject3&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

In the last step, provide a ``` Group Id ``` and ``` Artifact Id ``` as shown in the picture below and click ``` Finish ```.

![Create a new Maven Project - Step 4](https://apidocs.io/illustration/java?step=createNewProject4&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

### 2. Add reference of the library project

The created Maven project manages its dependencies using its ``` pom.xml ``` file. In order to add a dependency on the *UberAPILib* client library, double click on the ``` pom.xml ``` file in the ``` Package Explorer ```. Opening the ``` pom.xml ``` file will render a graphical view on the cavas. Here, switch to the ``` Dependencies ``` tab and click the ``` Add ``` button as shown in the picture below.

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/java?step=testProject0&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

Clicking the ``` Add ``` button will open a dialog where you need to specify UberAPILib in ``` Group Id ``` and UberAPILib in the ``` Artifact Id ``` fields. Once added click ``` OK ```. Save the ``` pom.xml ``` file.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/java?step=testProject1&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

### 3. Write sample code

Once the ``` SimpleConsoleApp ``` is created, a file named ``` App.java ``` will be visible in the *Package Explorer* with a ``` main ``` method. This is the entry point for the execution of the created project.
Here, you can add code to initialize the client library and instantiate a *Controller* class. Sample code to initialize the client library and using controller methods is given in the subsequent sections.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/java?step=testProject2&workspaceFolder=Uber%20API-Java&workspaceName=UberAPILib&projectName=UberAPILib&rootNamespace=com.acme.corp.api)

## How to Test

The generated code and the server can be tested using automatically generated test cases. 
JUnit is used as the testing framework and test runner.

In Eclipse, for running the tests do the following:

1. Select the project *UberAPILib* from the package explorer.
2. Select "Run -> Run as -> JUnit Test" or use "Alt + Shift + X" followed by "T" to run the Tests.

## Initialization

### 

API client can be initialized as following.

```java
// Initializing Object Mapper for Serialization and Deserialization purposes
public static ObjectMapper mapper = new ObjectMapper()
{
	private static final long serialVersionUID = -174113593500315394L;
	{
		configure(DeserializationFeature.FAIL_ON_UNKNOWN_PROPERTIES, false);
		setSerializationInclusion(JsonInclude.Include.NON_NULL);
	}
};


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
double startLatitude = 206.075520401856;
double startLongitude = 206.075520401856;
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
double startLatitude = 206.075520401856;
double startLongitude = 206.075520401856;
double endLatitude = 206.075520401856;
double endLongitude = 206.075520401856;
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



