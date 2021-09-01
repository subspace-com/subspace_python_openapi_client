# subspace_openapi_client.SipTeleportServiceApi

All URIs are relative to *https://api.subspace.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**sip_teleport_service_create**](SipTeleportServiceApi.md#sip_teleport_service_create) | **POST** /v1/sip-teleports | 
[**sip_teleport_service_delete**](SipTeleportServiceApi.md#sip_teleport_service_delete) | **DELETE** /v1/sip-teleports/{id} | 
[**sip_teleport_service_get**](SipTeleportServiceApi.md#sip_teleport_service_get) | **GET** /v1/sip-teleports/{id} | 
[**sip_teleport_service_list**](SipTeleportServiceApi.md#sip_teleport_service_list) | **GET** /v1/sip-teleports | 
[**sip_teleport_service_update**](SipTeleportServiceApi.md#sip_teleport_service_update) | **PUT** /v1/sip-teleports/{id} | 


# **sip_teleport_service_create**
> V1SipTeleportResponse sip_teleport_service_create(v1_create_sip_teleport)



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_create_sip_teleport import V1CreateSipTeleport
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
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
    api_instance = sip_teleport_service_api.SipTeleportServiceApi(api_client)
    v1_create_sip_teleport = V1CreateSipTeleport(
        name="name_example",
        destination="destination_example",
    ) # V1CreateSipTeleport | Required parameters to create a new SIPTeleport
    idempotency_key = "Idempotency-Key_example" # str | Value is the returned etag of a get request.  If a retry sends an Idempotency-Key that has been seen before, the existing teleport is returned with the status code of 200 (optional)

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.sip_teleport_service_create(v1_create_sip_teleport)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_create: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.sip_teleport_service_create(v1_create_sip_teleport, idempotency_key=idempotency_key)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_create: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **v1_create_sip_teleport** | [**V1CreateSipTeleport**](V1CreateSipTeleport.md)| Required parameters to create a new SIPTeleport |
 **idempotency_key** | **str**| Value is the returned etag of a get request.  If a retry sends an Idempotency-Key that has been seen before, the existing teleport is returned with the status code of 200 | [optional]

### Return type

[**V1SipTeleportResponse**](V1SipTeleportResponse.md)

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
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **sip_teleport_service_delete**
> V1SipTeleportResponse sip_teleport_service_delete(id)



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
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
    api_instance = sip_teleport_service_api.SipTeleportServiceApi(api_client)
    id = "id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.sip_teleport_service_delete(id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_delete: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**|  |

### Return type

[**V1SipTeleportResponse**](V1SipTeleportResponse.md)

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

# **sip_teleport_service_get**
> V1SipTeleportResponse sip_teleport_service_get(id)



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
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
    api_instance = sip_teleport_service_api.SipTeleportServiceApi(api_client)
    id = "id_example" # str | 

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.sip_teleport_service_get(id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_get: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**|  |

### Return type

[**V1SipTeleportResponse**](V1SipTeleportResponse.md)

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

# **sip_teleport_service_list**
> V1ListSipTeleportResponse sip_teleport_service_list()



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_list_sip_teleport_response import V1ListSipTeleportResponse
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
    api_instance = sip_teleport_service_api.SipTeleportServiceApi(api_client)
    before = "before_example" # str |  (optional)
    limit = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.sip_teleport_service_list(before=before, limit=limit)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **before** | **str**|  | [optional]
 **limit** | **int**|  | [optional]

### Return type

[**V1ListSipTeleportResponse**](V1ListSipTeleportResponse.md)

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

# **sip_teleport_service_update**
> V1SipTeleportResponse sip_teleport_service_update(id, v1_update_sip_teleport)



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_update_sip_teleport import V1UpdateSipTeleport
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
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
    api_instance = sip_teleport_service_api.SipTeleportServiceApi(api_client)
    id = "id_example" # str | 
    v1_update_sip_teleport = V1UpdateSipTeleport(
        name="name_example",
        destination="destination_example",
        status=V1SipTeleportStatus("DISABLED"),
    ) # V1UpdateSipTeleport | Parameters to update an existing SIPTeleport, minimum requirement of one of them defined to update

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.sip_teleport_service_update(id, v1_update_sip_teleport)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_update: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **id** | **str**|  |
 **v1_update_sip_teleport** | [**V1UpdateSipTeleport**](V1UpdateSipTeleport.md)| Parameters to update an existing SIPTeleport, minimum requirement of one of them defined to update |

### Return type

[**V1SipTeleportResponse**](V1SipTeleportResponse.md)

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
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

