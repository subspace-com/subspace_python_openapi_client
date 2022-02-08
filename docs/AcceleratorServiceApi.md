# subspace_openapi_client.AcceleratorServiceApi

All URIs are relative to *https://api.subspace.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**accelerator_service_create**](AcceleratorServiceApi.md#accelerator_service_create) | **POST** /v1/accelerator | 
[**accelerator_service_delete**](AcceleratorServiceApi.md#accelerator_service_delete) | **DELETE** /v1/accelerator/{id} | 
[**accelerator_service_get**](AcceleratorServiceApi.md#accelerator_service_get) | **GET** /v1/accelerator/{id} | 
[**accelerator_service_list**](AcceleratorServiceApi.md#accelerator_service_list) | **GET** /v1/accelerator | 
[**accelerator_service_update**](AcceleratorServiceApi.md#accelerator_service_update) | **PUT** /v1/accelerator/{id} | 


# **accelerator_service_create**
> V1Accelerator accelerator_service_create(body)



### Example

* OAuth Authentication (accessCode):

```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import accelerator_service_api
from subspace_openapi_client.model.v1_accelerator import V1Accelerator
from subspace_openapi_client.model.body import Body
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
    api_instance = accelerator_service_api.AcceleratorServiceApi(api_client)
    body = Body(
        name="name_example",
        destination_ip="destination_ip_example",
        destination_port=1,
        subspace_port=1,
    ) # Body | Required parameters to create a new PacketAccelerator.
    idempotency_key = "Idempotency-Key_example" # str | Value is the returned etag of a get request.  If a retry sends an Idempotency-Key that has been seen before, the existing accelerator is returned with the status code of 200 (optional)

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.accelerator_service_create(body)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_create: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.accelerator_service_create(body, idempotency_key=idempotency_key)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_create: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **body** | [**Body**](Body.md)| Required parameters to create a new PacketAccelerator. |
 **idempotency_key** | **str**| Value is the returned etag of a get request.  If a retry sends an Idempotency-Key that has been seen before, the existing accelerator is returned with the status code of 200 | [optional]

### Return type

[**V1Accelerator**](V1Accelerator.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**400** | Bad request |  -  |
**401** | Access token is missing or invalid |  -  |
**402** | Quota exceeded |  -  |
**403** | Not authorized |  -  |
**404** | Returned when the resource does not exist. |  -  |
**429** | Too many client requests |  -  |
**201** | Accelerator created |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **accelerator_service_delete**
> {str: (bool, date, datetime, dict, float, int, list, str, none_type)} accelerator_service_delete(id)



### Example

* OAuth Authentication (accessCode):

```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import accelerator_service_api
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
    api_instance = accelerator_service_api.AcceleratorServiceApi(api_client)
    id = "id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.accelerator_service_delete(id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_delete: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**|  |

### Return type

**{str: (bool, date, datetime, dict, float, int, list, str, none_type)}**

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**400** | Bad request |  -  |
**401** | Access token is missing or invalid |  -  |
**402** | Quota exceeded |  -  |
**403** | Not authorized |  -  |
**404** | Returned when the resource does not exist. |  -  |
**429** | Too many client requests |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **accelerator_service_get**
> V1Accelerator accelerator_service_get(id)



### Example

* OAuth Authentication (accessCode):

```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import accelerator_service_api
from subspace_openapi_client.model.v1_accelerator import V1Accelerator
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
    api_instance = accelerator_service_api.AcceleratorServiceApi(api_client)
    id = "id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.accelerator_service_get(id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_get: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**|  |

### Return type

[**V1Accelerator**](V1Accelerator.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  * ETag - Include in the headers of a subsequent PUT to avoid concurrency issues <br>  |
**400** | Bad request |  -  |
**401** | Access token is missing or invalid |  -  |
**402** | Quota exceeded |  -  |
**403** | Not authorized |  -  |
**404** | Returned when the resource does not exist. |  -  |
**429** | Too many client requests |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **accelerator_service_list**
> V1ListAcceleratorResponse accelerator_service_list()



### Example

* OAuth Authentication (accessCode):

```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import accelerator_service_api
from subspace_openapi_client.model.v1_list_accelerator_response import V1ListAcceleratorResponse
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
    api_instance = accelerator_service_api.AcceleratorServiceApi(api_client)
    before = "before_example" # str |  (optional)
    limit = 1 # int |  (optional)
    name = "name_example" # str |  (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.accelerator_service_list(before=before, limit=limit, name=name)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **before** | **str**|  | [optional]
 **limit** | **int**|  | [optional]
 **name** | **str**|  | [optional]

### Return type

[**V1ListAcceleratorResponse**](V1ListAcceleratorResponse.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**400** | Bad request |  -  |
**401** | Access token is missing or invalid |  -  |
**402** | Quota exceeded |  -  |
**403** | Not authorized |  -  |
**404** | Returned when the resource does not exist. |  -  |
**429** | Too many client requests |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **accelerator_service_update**
> V1Accelerator accelerator_service_update(id, body1)



### Example

* OAuth Authentication (accessCode):

```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import accelerator_service_api
from subspace_openapi_client.model.v1_accelerator import V1Accelerator
from subspace_openapi_client.model.body1 import Body1
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
    api_instance = accelerator_service_api.AcceleratorServiceApi(api_client)
    id = "id_example" # str | 
    body1 = Body1(
        name="name_example",
    ) # Body1 | Parameters to update an existing PacketAccelerator
    if_match = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.accelerator_service_update(id, body1)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_update: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.accelerator_service_update(id, body1, if_match=if_match)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_update: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**|  |
 **body1** | [**Body1**](Body1.md)| Parameters to update an existing PacketAccelerator |
 **if_match** | **int**|  | [optional]

### Return type

[**V1Accelerator**](V1Accelerator.md)

### Authorization

[accessCode](../README.md#accessCode)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | A successful response. |  -  |
**400** | Bad request |  -  |
**401** | Access token is missing or invalid |  -  |
**402** | Quota exceeded |  -  |
**403** | Not authorized |  -  |
**404** | Returned when the resource does not exist. |  -  |
**429** | Too many client requests |  -  |
**409** | Edit conflict |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

