# subspace_openapi_client.SipTeleportServiceApi

All URIs are relative to *https://api.subspace.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**sip_teleport_service_create**](SipTeleportServiceApi.md#sip_teleport_service_create) | **POST** /v1/sip-teleports | CreateSipTeleport
[**sip_teleport_service_delete**](SipTeleportServiceApi.md#sip_teleport_service_delete) | **DELETE** /v1/sip-teleports/{id} | DeleteSipTeleport
[**sip_teleport_service_get**](SipTeleportServiceApi.md#sip_teleport_service_get) | **GET** /v1/sip-teleports/{id} | GetSipTeleport
[**sip_teleport_service_list**](SipTeleportServiceApi.md#sip_teleport_service_list) | **GET** /v1/sip-teleports | ListSipTeleports
[**sip_teleport_service_update**](SipTeleportServiceApi.md#sip_teleport_service_update) | **PUT** /v1/sip-teleports/{id} | UpdateSipTeleport


# **sip_teleport_service_create**
> V1SipTeleportResponse sip_teleport_service_create()

CreateSipTeleport

CreateSipTeleport creates a new SIP Teleport

### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
from subspace_openapi_client.model.rpc_status import RpcStatus
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

    # example, this endpoint has no required or optional parameters
    try:
        # CreateSipTeleport
        api_response = api_instance.sip_teleport_service_create()
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_create: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

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
**401** | Returned when the user does not have permission to access the resource. |  -  |
**404** | Returned when the resource does not exist. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **sip_teleport_service_delete**
> V1SipTeleportResponse sip_teleport_service_delete(id)

DeleteSipTeleport

DeleteSipTeleport deletes an existing SIP Teleport, specified by its id

### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
from subspace_openapi_client.model.rpc_status import RpcStatus
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
        # DeleteSipTeleport
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
**401** | Returned when the user does not have permission to access the resource. |  -  |
**404** | Returned when the resource does not exist. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **sip_teleport_service_get**
> V1SipTeleportResponse sip_teleport_service_get(id)

GetSipTeleport

GetSipTeleport fetches the details of a specific SIP Teleport, specified by its id

### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
from subspace_openapi_client.model.rpc_status import RpcStatus
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
        # GetSipTeleport
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
**200** | A successful response. |  -  |
**401** | Returned when the user does not have permission to access the resource. |  -  |
**404** | Returned when the resource does not exist. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **sip_teleport_service_list**
> V1ListSipTeleportResponse sip_teleport_service_list()

ListSipTeleports

ListSipTeleports lists all SIP Teleports

### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_list_sip_teleport_response import V1ListSipTeleportResponse
from subspace_openapi_client.model.rpc_status import RpcStatus
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
        # ListSipTeleports
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
**401** | Returned when the user does not have permission to access the resource. |  -  |
**404** | Returned when the resource does not exist. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **sip_teleport_service_update**
> V1SipTeleportResponse sip_teleport_service_update(id)

UpdateSipTeleport

UpdateSipTeleport updates an existing SIP Teleport, specified by its id

### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import sip_teleport_service_api
from subspace_openapi_client.model.v1_sip_teleport_response import V1SipTeleportResponse
from subspace_openapi_client.model.rpc_status import RpcStatus
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
        # UpdateSipTeleport
        api_response = api_instance.sip_teleport_service_update(id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SipTeleportServiceApi->sip_teleport_service_update: %s\n" % e)
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
**401** | Returned when the user does not have permission to access the resource. |  -  |
**404** | Returned when the resource does not exist. |  -  |
**0** | An unexpected error response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

