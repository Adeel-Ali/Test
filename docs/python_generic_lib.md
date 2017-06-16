# Getting started

## How to Build


You must have Python 2 >=2.7.9 or Python 3 >=3.4 installed on your system to install and run this SDK. This SDK package depends on other Python packages like nose, jsonpickle etc. 
These dependencies are defined in the ```requirements.txt``` file that comes with the SDK.
To resolve these dependencies, you can use the PIP Dependency manager. Install it by following steps at [https://pip.pypa.io/en/stable/installing/](https://pip.pypa.io/en/stable/installing/).

Python and PIP executables should be defined in your PATH. Open command prompt and type ```pip --version```.
This should display the version of the PIP Dependency Manager installed if your installation was successful and the paths are properly defined.

* Using command line, navigate to the directory containing the generated files (including ```requirements.txt```) for the SDK.
* Run the command ```pip install -r requirements.txt```. This should install all the required dependencies.

![Building SDK - Step 1](https://apidocs.io/illustration/python?step=installDependencies&workspaceFolder=Uber%20API-Python)


## How to Use

The following section explains how to use the Uberapi SDK package in a new project.

### 1. Open Project in an IDE

Open up a Python IDE like PyCharm. The basic workflow presented here is also applicable if you prefer using a different editor or IDE.

![Open project in PyCharm - Step 1](https://apidocs.io/illustration/python?step=pyCharm)

Click on ```Open``` in PyCharm to browse to your generated SDK directory and then click ```OK```.

![Open project in PyCharm - Step 2](https://apidocs.io/illustration/python?step=openProject0&workspaceFolder=Uber%20API-Python)     

The project files will be displayed in the side bar as follows:

![Open project in PyCharm - Step 3](https://apidocs.io/illustration/python?step=openProject1&workspaceFolder=Uber%20API-Python&projectName=uberapi)     

### 2. Add a new Test Project

Create a new directory by right clicking on the solution name as shown below:

![Add a new project in PyCharm - Step 1](https://apidocs.io/illustration/python?step=createDirectory&workspaceFolder=Uber%20API-Python&projectName=uberapi)

Name the directory as "test"

![Add a new project in PyCharm - Step 2](https://apidocs.io/illustration/python?step=nameDirectory)
   
Add a python file to this project with the name "testsdk"

![Add a new project in PyCharm - Step 3](https://apidocs.io/illustration/python?step=createFile&workspaceFolder=Uber%20API-Python&projectName=uberapi)

Name it "testsdk"

![Add a new project in PyCharm - Step 4](https://apidocs.io/illustration/python?step=nameFile)

In your python file you will be required to import the generated python library using the following code lines

```Python
from uberapi.uberapi_client.py import *
```

![Add a new project in PyCharm - Step 4](https://apidocs.io/illustration/python?step=projectFiles&workspaceFolder=Uber%20API-Python&libraryName=uberapi.uberapi_client.py&projectName=uberapi)

After this you can write code to instantiate an API client object, get a controller object and  make API calls. Sample code is given in the subsequent sections.

### 3. Run the Test Project

To run the file within your test project, right click on your Python file inside your Test project and click on ```Run```

![Run Test Project - Step 1](https://apidocs.io/illustration/python?step=runProject&workspaceFolder=Uber%20API-Python&libraryName=uberapi.uberapi_client.py&projectName=uberapi)


## How to Test

You can test the generated SDK and the server with automatically generated test
cases. unittest is used as the testing framework and nose is used as the test
runner. You can run the tests as follows:

  1. From terminal/cmd navigate to the root directory of the SDK.
  2. Invoke 'pip install -r test-requirements.txt'
  3. Invoke 'nosetests'

## Initialization

### 

API client can be initialized as following.

```python

client = UberapiClient()
```

# Class Reference

## <a name="list_of_controllers"></a>List of Controllers

* [UserController](#user_controller)
* [EstimatesController](#estimates_controller)
* [ProductsController](#products_controller)

## <a name="user_controller"></a>![Class: ](https://apidocs.io/img/class.png ".UserController") UserController

### Get controller instance

An instance of the ``` UserController ``` class can be accessed from the API Client.

```python
 user_client = client.user
```

### <a name="get_history"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.get_history") get_history

> *Tags:*  ``` Skips Authentication ``` 

> User Activity

```python
def get_history(self,
                    offset=None,
                    limit=None)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| offset |  ``` Optional ```  | Offset the list of returned results by this amount. Default is zero. |
| limit |  ``` Optional ```  | Number of items to retrieve. Default is 5, maximum is 100. |



#### Example Usage

```python
offset = 2
limit = 10

result = user_client.get_history(offset, limit)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




### <a name="get_me"></a>![Method: ](https://apidocs.io/img/method.png ".UserController.get_me") get_me

> *Tags:*  ``` Skips Authentication ``` 

> User Profile

```python
def get_me(self)
```

#### Example Usage

```python

result = user_client.get_me()

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)

## <a name="estimates_controller"></a>![Class: ](https://apidocs.io/img/class.png ".EstimatesController") EstimatesController

### Get controller instance

An instance of the ``` EstimatesController ``` class can be accessed from the API Client.

```python
 estimates_client = client.estimates
```

### <a name="get_estimates_time"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.get_estimates_time") get_estimates_time

> *Tags:*  ``` Skips Authentication ``` 

> Time Estimates

```python
def get_estimates_time(self,
                           start_latitude,
                           start_longitude,
                           customer_uuid=None,
                           product_id=None)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| customerUuid |  ``` Optional ```  | Unique customer identifier to be used for experience customization. |
| productId |  ``` Optional ```  | Unique identifier representing a specific product for a given latitude & longitude. |



#### Example Usage

```python
start_latitude = 64.8081298450977
start_longitude = 64.8081298450977
customer_uuid = uuid.uuid4()
product_id = 'product_id'

result = estimates_client.get_estimates_time(start_latitude, start_longitude, customer_uuid, product_id)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




### <a name="get_estimates_price"></a>![Method: ](https://apidocs.io/img/method.png ".EstimatesController.get_estimates_price") get_estimates_price

> *Tags:*  ``` Skips Authentication ``` 

> Price Estimates

```python
def get_estimates_price(self,
                            start_latitude,
                            start_longitude,
                            end_latitude,
                            end_longitude)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| startLatitude |  ``` Required ```  | Latitude component of start location. |
| startLongitude |  ``` Required ```  | Longitude component of start location. |
| endLatitude |  ``` Required ```  | Latitude component of end location. |
| endLongitude |  ``` Required ```  | Longitude component of end location. |



#### Example Usage

```python
start_latitude = 64.8081298450977
start_longitude = 64.8081298450977
end_latitude = 64.8081298450977
end_longitude = 64.8081298450977

result = estimates_client.get_estimates_price(start_latitude, start_longitude, end_latitude, end_longitude)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)

## <a name="products_controller"></a>![Class: ](https://apidocs.io/img/class.png ".ProductsController") ProductsController

### Get controller instance

An instance of the ``` ProductsController ``` class can be accessed from the API Client.

```python
 products_client = client.products
```

### <a name="get_products"></a>![Method: ](https://apidocs.io/img/method.png ".ProductsController.get_products") get_products

> *Tags:*  ``` Skips Authentication ``` 

> Product Types

```python
def get_products(self,
                     latitude,
                     longitude)
```

#### Parameters

| Parameter | Tags | Description |
|-----------|------|-------------|
| latitude |  ``` Required ```  | Latitude component of location. |
| longitude |  ``` Required ```  | Longitude component of location. |



#### Example Usage

```python
latitude = 12.5
longitude = 555.6

result = products_client.get_products(latitude, longitude)

```

#### Errors

| Error Code | Error Description |
|------------|-------------------|
| 0 | Unexpected error |




[Back to List of Controllers](#list_of_controllers)



