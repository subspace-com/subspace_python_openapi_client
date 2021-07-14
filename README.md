# subspace-openapi-client
# Introduction

The Subspace API is based on REST, has resource-oriented URLs, returns JSON-encoded responses, and returns standardHTTP response codes.

The base URL for the API is `https://api.subspace.com/`

# Naming Convention

**EARLY ACCESS NOTE:** There is no “stable” version yet.  Once there is, the version name **stable** will be used to access the latest stable API version.
  * Example: `https://api.subspace.com/stable`
* Version name currently in use is: *v1*
  * Example: `https://api.subspace.com/v1`

# Authentication

## API Tokens

Subspace authenticates your API requests using JWT Bearer tokens.  The provided client library requires this JWT to be set before it can be used, by setting the local access token in the local configuration.  This is done by updating the configuration line marked \"YOUR ACCESS TOKEN\" by replacing the text \"YOUR ACCESS TOKEN\" with your JWT Bearer token.

Bearer tokens are granted by requesting one (as noted below) and presenting your publishable (client_id) and secret (client_secret) tokens.   

Subspace provides two types of API tokens: publishable (client_id) and secret (client_secret).  These are available in the Subspace console.
  * **Publishable** API tokens (client_id) are meant solely to identify your account with Subspace, they aren’t secret. They can be published in places like your website JavaScript code, or in an iPhone or Android app.
  * **Secret** API tokens (client_secret) should be kept confidential and only stored on your own servers. Your account’s secret API token will allow you to acquire a valid JWT token authorized to perform any API request to Subspace.

## Getting a JWT Bearer Token

Subspace uses auth0 for JWT token management.  You can acquire a JWT token by utilizing `https://id.subspace.com` and following the instructions in the curl example below.

## Protecting Your API Tokens

  * **JWT tokens have a expiration time of 24 hours.**  Once expired, you will have to use your Subspace private API and public token to request a new one.
  * The Subspace private token can be rotated from within the Subspace console.  Rotation may take up to 10 minutes for all systems to update state to invalidate the older token and enable the new one.
* **Keep your secret token safe.** Your secret token can make any API call on behalf of your account, including changes that may impact billing such as enabling pay-as-you-go charges. Do not store your secret token in your version control system. Do not use your secret token outside your web server, such as a browser, mobile app, or distributed file.
  * **You may use the Subspace console to acquire an API token.**
 * **You may use the Subspace console to disable pay-as-you-go.** This may prevent unexpected charges due to unauthorized or abnormal usage.

**Acquiring a valid JWT**

Command line example:
```
curl --request POST 
         --url 'https://id.subspace.com/oauth/token' 
         --header 'content-type: application/json' 
         --data '{ \"client_id\": YOURCLIENTID, \"client_secret\": YOURCLIENTSECRET, \"audience\": \"https://api.subspace.com/\", \"grant_type\": \"client_credentials\" }'
```


This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0
- Package version: 1.0.0
- Build package: org.openapitools.codegen.languages.PythonClientCodegen
For more information, please visit [https://subspace.com](https://subspace.com)

## Requirements.

Python >= 3.6

## Installation & Usage
### pip install

If the python package is hosted on a repository, you can install directly using:

```sh
pip install git+https://github.com/subspace-com/subspace_python_openapi_client.git
```
(you may need to run `pip` with root permission: `sudo pip install git+https://github.com/subspace-com/subspace_python_openapi_client.git`)

Then import the package:
```python
import subspace_openapi_client
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import subspace_openapi_client
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import time
import subspace_openapi_client
from pprint import pprint
from subspace_openapi_client.api import accelerator_service_api
from subspace_openapi_client.model.body import Body
from subspace_openapi_client.model.body1 import Body1
from subspace_openapi_client.model.rpc_status import RpcStatus
from subspace_openapi_client.model.v1_accelerator import V1Accelerator
from subspace_openapi_client.model.v1_list_accelerators_response import V1ListAcceleratorsResponse
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
        protocol="protocol_example",
        name="name_example",
        destination_ip="destination_ip_example",
        destination_port=1,
        subspace_port=1,
    ) # Body | Required parameters to create a new PacketAccelerator.  NOTE- only subspace_port is optional
idempotency_key = "Idempotency-Key_example" # str | Value is the returned etag of a get request.  If a retry sends an Idempotency-Key that has been seen before, the existing accelerator is returned with the status code of 200 (optional)

    try:
        # CreateAccelerator
        api_response = api_instance.accelerator_service_create(body, idempotency_key=idempotency_key)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_create: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://api.subspace.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AcceleratorServiceApi* | [**accelerator_service_create**](docs/AcceleratorServiceApi.md#accelerator_service_create) | **POST** /v1/accelerators | CreateAccelerator
*AcceleratorServiceApi* | [**accelerator_service_delete**](docs/AcceleratorServiceApi.md#accelerator_service_delete) | **DELETE** /v1/accelerators/{id} | DeleteAccelerator
*AcceleratorServiceApi* | [**accelerator_service_get**](docs/AcceleratorServiceApi.md#accelerator_service_get) | **GET** /v1/accelerators/{id} | GetAccelerator
*AcceleratorServiceApi* | [**accelerator_service_list**](docs/AcceleratorServiceApi.md#accelerator_service_list) | **GET** /v1/accelerators | ListAccelerators
*AcceleratorServiceApi* | [**accelerator_service_update**](docs/AcceleratorServiceApi.md#accelerator_service_update) | **PUT** /v1/accelerators/{id} | UpdateAccelerator
*SipTeleportServiceApi* | [**sip_teleport_service_create**](docs/SipTeleportServiceApi.md#sip_teleport_service_create) | **POST** /v1/sip-teleports | CreateSipTeleport
*SipTeleportServiceApi* | [**sip_teleport_service_delete**](docs/SipTeleportServiceApi.md#sip_teleport_service_delete) | **DELETE** /v1/sip-teleports/{id} | DeleteSipTeleport
*SipTeleportServiceApi* | [**sip_teleport_service_get**](docs/SipTeleportServiceApi.md#sip_teleport_service_get) | **GET** /v1/sip-teleports/{id} | GetSipTeleport
*SipTeleportServiceApi* | [**sip_teleport_service_list**](docs/SipTeleportServiceApi.md#sip_teleport_service_list) | **GET** /v1/sip-teleports | ListSipTeleports
*SipTeleportServiceApi* | [**sip_teleport_service_update**](docs/SipTeleportServiceApi.md#sip_teleport_service_update) | **PUT** /v1/sip-teleports/{id} | UpdateSipTeleport


## Documentation For Models

 - [Body](docs/Body.md)
 - [Body1](docs/Body1.md)
 - [ProtobufAny](docs/ProtobufAny.md)
 - [RpcStatus](docs/RpcStatus.md)
 - [V1Accelerator](docs/V1Accelerator.md)
 - [V1ListAcceleratorsResponse](docs/V1ListAcceleratorsResponse.md)
 - [V1ListSipTeleportResponse](docs/V1ListSipTeleportResponse.md)
 - [V1NextPage](docs/V1NextPage.md)
 - [V1Protocol](docs/V1Protocol.md)
 - [V1SipTeleportResponse](docs/V1SipTeleportResponse.md)
 - [V1SipTeleportStatus](docs/V1SipTeleportStatus.md)
 - [V1TeleportAddresses](docs/V1TeleportAddresses.md)
 - [V1TransportType](docs/V1TransportType.md)


## Documentation For Authorization


## accessCode

- **Type**: OAuth
- **Flow**: application
- **Authorization URL**: 
- **Scopes**: 
 - **accelerators:read**: allows reading details about provisioned PacketAccelerators
 - **accelerators:write**: allows administration of PacketAccelerators
 - **sipteleport:read**: allows reading details about provisioned SIPTeleport
 - **sipteleport:write**: allows administration of SIPTeleport


## Author

sales@subspace.com


## Notes for Large OpenAPI documents
If the OpenAPI document is large, imports in subspace_openapi_client.apis and subspace_openapi_client.models may fail with a
RecursionError indicating the maximum recursion limit has been exceeded. In that case, there are a couple of solutions:

Solution 1:
Use specific imports for apis and models like:
- `from subspace_openapi_client.api.default_api import DefaultApi`
- `from subspace_openapi_client.model.pet import Pet`

Solution 2:
Before importing the package, adjust the maximum recursion limit as shown below:
```
import sys
sys.setrecursionlimit(1500)
import subspace_openapi_client
from subspace_openapi_client.apis import *
from subspace_openapi_client.models import *
```
