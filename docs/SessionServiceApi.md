# subspace_openapi_client.SessionServiceApi

All URIs are relative to *https://api.subspace.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**session_service_list**](SessionServiceApi.md#session_service_list) | **GET** /v1/accelerators/{accelerator_id}/sessions | 


# **session_service_list**
> V1ListSessionsResponse session_service_list(accelerator_id)



### Example

* OAuth Authentication (accessCode):
```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import session_service_api
from subspace_openapi_client.model.v1_list_sessions_response import V1ListSessionsResponse
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
    api_instance = session_service_api.SessionServiceApi(api_client)
    accelerator_id = "accelerator_id_example" # str | 
    before = "before_example" # str |  (optional)
    limit = 1 # int |  (optional)

    # example passing only required values which don't have defaults set
    try:
        api_response = api_instance.session_service_list(accelerator_id)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SessionServiceApi->session_service_list: %s\n" % e)

    # example passing only required values which don't have defaults set
    # and optional values
    try:
        api_response = api_instance.session_service_list(accelerator_id, before=before, limit=limit)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling SessionServiceApi->session_service_list: %s\n" % e)
```


### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **accelerator_id** | **str**|  |
 **before** | **str**|  | [optional]
 **limit** | **int**|  | [optional]

### Return type

[**V1ListSessionsResponse**](V1ListSessionsResponse.md)

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

