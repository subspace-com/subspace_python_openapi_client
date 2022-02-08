# subspace_openapi_client.WebRtcCdnServiceApi

All URIs are relative to *https://api.subspace.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**web_rtc_cdn_service_get_web_rtc_cdn**](WebRtcCdnServiceApi.md#web_rtc_cdn_service_get_web_rtc_cdn) | **POST** /v1/webrtc-cdn | 


# **web_rtc_cdn_service_get_web_rtc_cdn**
> V1WebRtcCdnResponse web_rtc_cdn_service_get_web_rtc_cdn()



### Example

* OAuth Authentication (accessCode):

```python
import time
import subspace_openapi_client
from subspace_openapi_client.api import web_rtc_cdn_service_api
from subspace_openapi_client.model.v1_web_rtc_cdn_response import V1WebRtcCdnResponse
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
    api_instance = web_rtc_cdn_service_api.WebRtcCdnServiceApi(api_client)

    # example, this endpoint has no required or optional parameters
    try:
        api_response = api_instance.web_rtc_cdn_service_get_web_rtc_cdn()
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling WebRtcCdnServiceApi->web_rtc_cdn_service_get_web_rtc_cdn: %s\n" % e)
```


### Parameters
This endpoint does not need any parameter.

### Return type

[**V1WebRtcCdnResponse**](V1WebRtcCdnResponse.md)

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

