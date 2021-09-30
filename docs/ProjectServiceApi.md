# subspace_openapi_client.ProjectServiceApi

All URIs are relative to *https://api.subspace.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**project_service_create**](ProjectServiceApi.md#project_service_create) | **POST** /v1/project | 
[**project_service_get**](ProjectServiceApi.md#project_service_get) | **GET** /v1/project/{id} | 
[**project_service_list**](ProjectServiceApi.md#project_service_list) | **GET** /v1/project | 
[**project_service_update**](ProjectServiceApi.md#project_service_update) | **PUT** /v1/project/{id} | 


# **project_service_create**
> V1Project project_service_create()



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import project_service_api
from subspace_openapi_client.model.v1_project import V1Project
from pprint import pprint
# Defining the host is optional and defaults to https://api.subspace.com
# See configuration.py for a list of all supported configuration parameters.
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: accessCode
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with subspace_openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = project_service_api.ProjectServiceApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        api_response = api_instance.project_service_create()
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling ProjectServiceApi->project_service_create: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**V1Project**](V1Project.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **project_service_get**
> V1Project project_service_get(id)



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import project_service_api
from subspace_openapi_client.model.v1_project import V1Project
from pprint import pprint
# Defining the host is optional and defaults to https://api.subspace.com
# See configuration.py for a list of all supported configuration parameters.
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: accessCode
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with subspace_openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = project_service_api.ProjectServiceApi(api_client)
    id = "id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.project_service_get(id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling ProjectServiceApi->project_service_get: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**|  |

### Return type

[**V1Project**](V1Project.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **project_service_list**
> V1ListProjectsResponse project_service_list()



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import project_service_api
from subspace_openapi_client.model.v1_list_projects_response import V1ListProjectsResponse
from pprint import pprint
# Defining the host is optional and defaults to https://api.subspace.com
# See configuration.py for a list of all supported configuration parameters.
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: accessCode
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with subspace_openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = project_service_api.ProjectServiceApi(api_client)
    before = "before_example" # str |  (optional)
    limit = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.project_service_list(before=before, limit=limit)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling ProjectServiceApi->project_service_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **before** | **str**|  | [optional]
 **limit** | **int**|  | [optional]

### Return type

[**V1ListProjectsResponse**](V1ListProjectsResponse.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **project_service_update**
> V1Project project_service_update(id)



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import project_service_api
from subspace_openapi_client.model.v1_project import V1Project
from pprint import pprint
# Defining the host is optional and defaults to https://api.subspace.com
# See configuration.py for a list of all supported configuration parameters.
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)

# The client must configure the authentication and authorization parameters
# in accordance with the API server security policy.
# Examples for each auth method are provided below, use the example that
# satisfies your auth use case.

# Configure OAuth2 access token for authorization: accessCode
configuration = subspace_openapi_client.Configuration(
    host = "https://api.subspace.com"
)
configuration.access_token = 'YOUR_ACCESS_TOKEN'

# Enter a context with an instance of the API client
with subspace_openapi_client.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = project_service_api.ProjectServiceApi(api_client)
    id = "id_example" # str | id is the project identity

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.project_service_update(id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling ProjectServiceApi->project_service_update: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**| id is the project identity |

### Return type

[**V1Project**](V1Project.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

