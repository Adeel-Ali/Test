# Getting started

## How to Build


* In order to successfully build and run your SDK files, you are required to have the following setup in your system:
    * **Go**  (Visit [https://golang.org/doc/install](https://golang.org/doc/install) for more details on how to install Go)
    * **Java VM** Version 8 or later
    * **Eclipse 4.6 (Neon)** or later ([http://www.eclipse.org/neon/](http://www.eclipse.org/neon/))
    * **GoClipse** setup within above installed Eclipse (Follow the instructions at [this link](https://github.com/GoClipse/goclipse/blob/latest/documentation/Installation.md#instructions) to setup GoClipse)
* Ensure that ```GOPATH``` environment variable is set in the system variables. If not, set it to your workspace directory where you will be adding your Go projects.
* The generated code uses unirest-go http library. Therefore, you will need internet access to resolve this dependency. If Go is properly installed and configured, run the following command to pull the dependency:

```Go
go get github.com/apimatic/unirest-go
```

This will install unirest-go in the ```GOPATH``` you specified in the system variables.

Now follow the steps mentioned below to build your SDK:

1. Open eclipse in the Go language perspective and click on the ```Import``` option in ```File``` menu.

![Importing SDK into Eclipse - Step 1](https://apidocs.io/illustration/go?step=import0)

2. Select ```General -> Existing Projects into Workspace``` option from the tree list.

![Importing SDK into Eclipse - Step 2](https://apidocs.io/illustration/go?step=import1)

3. In ```Select root directory```, provide path to the unzipped archive for the generated code. Once the path is set and the Project becomes visible under ```Projects``` click ```Finish```

![Importing SDK into Eclipse - Step 3](https://apidocs.io/illustration/go?step=import2&workspaceFolder=Uber%20API-GoLang&projectName=uberapi_lib)

4. The Go library will be imported and its files will be visible in the Project Explorer

![Importing SDK into Eclipse - Step 4](https://apidocs.io/illustration/go?step=import3&projectName=uberapi_lib)

## How to Use

The following section explains how to use the UberapiLib library in a new project.

### 1. Add a new Test Project

Create a new project in Eclipse by ```File``` -> ```New``` -> ```Go Project```

![Add a new project in Eclipse](https://apidocs.io/illustration/go?step=createNewProject0)

Name the Project as ```Test``` and click ```Finish```

![Create a new Maven Project - Step 1](https://apidocs.io/illustration/go?step=createNewProject1)

Create a new directory in the ```src``` directory of this project

![Create a new Maven Project - Step 2](https://apidocs.io/illustration/go?step=createNewProject2&projectName=uberapi_lib)

Name it ```test.com```

![Create a new Maven Project - Step 3](https://apidocs.io/illustration/go?step=createNewProject3&projectName=uberapi_lib)

Now create a new file inside ```src/test.com```

![Create a new Maven Project - Step 4](https://apidocs.io/illustration/go?step=createNewProject4&projectName=uberapi_lib)

Name it ```testsdk.go```

![Create a new Maven Project - Step 5](https://apidocs.io/illustration/go?step=createNewProject5&projectName=uberapi_lib)

In this Go file, you can start adding code to initialize the client library. Sample code to initialize the client library and using its methods is given in the subsequent sections.

### 2. Configure the Test Project

You need to import your generated library in this project in order to make use of its functions. In order to import the library, you can add its path in the ```GOPATH``` for this project. Follow the below steps:

Right click on the project name and click on ```Properties```

![Adding dependency to the client library - Step 1](https://apidocs.io/illustration/go?step=testProject0&projectName=uberapi_lib)

Choose ```Go Compiler``` from the side menu. Check ```Use project specific settings``` and uncheck ```Use same value as the GOPATH environment variable.```. By default, the GOPATH value from the environment variables will be visible in ```Eclipse GOPATH```. Do not remove this as this points to the unirest dependency.

![Adding dependency to the client library - Step 2](https://apidocs.io/illustration/go?step=testProject1)

Append the library path to this GOPATH

![Adding dependency to the client library - Step 3](https://apidocs.io/illustration/go?step=testProject2&workspaceFolder=Uber%20API-GoLang)

Once the path is appended, click on ```OK```

### 3. Build the Test Project

Right click on the project name and click on ```Build Project```

![Build Project](https://apidocs.io/illustration/go?step=buildProject&projectName=uberapi_lib)

### 4. Run the Test Project

If the build is successful, right click on your Go file and click on ```Run As``` -> ```Go Application```

![Run Project](https://apidocs.io/illustration/go?step=runProject&projectName=uberapi_lib)

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [user_pkg](#user_pkg)
* [estimates_pkg](#estimates_pkg)
* [products_pkg](#products_pkg)

## <a name="user_pkg"></a>![Class: ](https://apidocs.io/img/class.png ".user_pkg") user_pkg

### Get instance

Factory for the ``` USER ``` interface can be accessed from the package user_pkg.

```go
user := user_pkg.NewUSER()
```

### <a name="get_history"></a>![Method: ](https://apidocs.io/img/method.png ".user_pkg.GetHistory") GetHistory

> *Tags:*  ``` Skips Authentication ``` 

> User Activity


```go
func (me *USER_IMPL) GetHistory(
            offset *int64,
            limit *int64)(*models_pkg.ActivitiesModel,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |


#### Example Usage

```go
offset,_ := strconv.ParseInt("2", 10, 8)
limit,_ := strconv.ParseInt("10", 10, 8)

var result *models_pkg.ActivitiesModel
result,_ = user.GetHistory(offset, limit)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_me"></a>![Method: ](https://apidocs.io/img/method.png ".user_pkg.GetMe") GetMe

> *Tags:*  ``` Skips Authentication ``` 

> User Profile


```go
func (me *USER_IMPL) GetMe()(*models_pkg.ProfileModel,error)
```

#### Example Usage

```go

var result *models_pkg.ProfileModel
result,_ = user.GetMe()

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_pkg"></a>![Class: ](https://apidocs.io/img/class.png ".estimates_pkg") estimates_pkg

### Get instance

Factory for the ``` ESTIMATES ``` interface can be accessed from the package estimates_pkg.

```go
estimates := estimates_pkg.NewESTIMATES()
```

### <a name="get_estimates_time"></a>![Method: ](https://apidocs.io/img/method.png ".estimates_pkg.GetEstimatesTime") GetEstimatesTime

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates


```go
func (me *ESTIMATES_IMPL) GetEstimatesTime(
            startLatitude float64,
            startLongitude float64,
            customerUuid *uuid.UUID,
            productId *string)([]*models_pkg.ProductModel,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| customerUuid |  ``` Optional ```  | Unique customer identifier to be used for experience customization. |
| productId |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. |


#### Example Usage

```go
startLatitude := 156.30341173676
startLongitude := 156.30341173676
customerUuid := uuid.NewV4()
productId := "product_id"

var result []*models_pkg.ProductModel
result,_ = estimates.GetEstimatesTime(startLatitude, startLongitude, customerUuid, productId)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



### <a name="get_estimates_price"></a>![Method: ](https://apidocs.io/img/method.png ".estimates_pkg.GetEstimatesPrice") GetEstimatesPrice

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates


```go
func (me *ESTIMATES_IMPL) GetEstimatesPrice(
            startLatitude float64,
            startLongitude float64,
            endLatitude float64,
            endLongitude float64)([]*models_pkg.PriceEstimateModel,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |


#### Example Usage

```go
startLatitude := 156.30341173676
startLongitude := 156.30341173676
endLatitude := 156.30341173676
endLongitude := 156.30341173676

var result []*models_pkg.PriceEstimateModel
result,_ = estimates.GetEstimatesPrice(startLatitude, startLongitude, endLatitude, endLongitude)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)

## <a name="products_pkg"></a>![Class: ](https://apidocs.io/img/class.png ".products_pkg") products_pkg

### Get instance

Factory for the ``` PRODUCTS ``` interface can be accessed from the package products_pkg.

```go
products := products_pkg.NewPRODUCTS()
```

### <a name="get_products"></a>![Method: ](https://apidocs.io/img/method.png ".products_pkg.GetProducts") GetProducts

> *Tags:*  ``` Skips Authentication ``` 

> Product Types


```go
func (me *PRODUCTS_IMPL) GetProducts(
            latitude float64,
            longitude float64)([]*models_pkg.ProductModel,error)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |


#### Example Usage

```go
latitude := "12.5"
longitude := "555.6"

var result []*models_pkg.ProductModel
result,_ = products.GetProducts(latitude, longitude)

```

#### Errors
 
| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |



[Back to List of Controllers](#list_of_controllers)



