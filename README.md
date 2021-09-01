# subspace-openapi-client
# Introduction

The Subspace API is based on REST, has resource-oriented URLs, returns JSON-encoded responses, and returns standard HTTP response codes.

The base URL for the API is:  `https://api.subspace.com/`

# Naming Convention

* Version name currently in use is: *v1*
  * Example: `https://api.subspace.com/v1`

# Authentication

## API Tokens

Subspace authenticates your API requests using JWT Bearer tokens. The provided client library requires this JWT to be set before it can be used, by setting the local access token in the local configuration.  This is done by updating the configuration line marked \"YOUR ACCESS TOKEN\" by replacing the text \"YOUR ACCESS TOKEN\" with your JWT Bearer token

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
  * **Do not embed API keys directly in code.** Instead of directly embedding API keys in your application’s code, put them in environment variables, or within include files that are stored separately from the bulk of your code—outside the source repository of your application. Then, if you share your code, the API keys will not be included in the shared files.
  * **Do not store API tokens inside your application’s source control.** If you store API tokens in files, keep the files outside your application’s source control system. This is particularly important if you use a public source code management system such as GitHub.
  * **Limit access with restricted tokens.** The Subspace console will allow you to specify the IP addresses or referrer URLs associated with each token, reducing the impact of a compromised API token.
  * **Use independent API tokens for different apps.** This limits the scope of each token. If an API token is compromised, you can rotate the impacted token without impacting other API tokens.


# Error Codes

Subspace uses HTTP response codes to indicate the success or failure of an API request. 

General HTML status codes:
  * 2xx Success. 
  * 4xx Errors based on information provided in the request.
  * 5xx Errors on Subspace servers.
  
# Security

We provide a valid, signed certificate for our API methods. Be sure your connection library supports HTTPS with the SNI extension.

# REST How-To

Making your first REST API call is easy and can be done from your browser.  You will need:
  * Your **secret** token and public client token, both found in the Console.
  * The URL for the type of data you would like to request.

First, acquire a JWT Bearer Token.  Command line example:
    
```
    curl --request POST \\
         --url \"https://id.subspace.com/oauth/token\" \\
         --header 'content-type: application/json' \\
         --data '{ \"client_id\": YOURCLIENTID, \"client_secret\": YOURCLIENTSECRET, \"audience\": \"https://api.subspace.com/\", \"grant_type\": \"client_credentials\" }'
```

REST calls are made up of:
  * Base url: Example: `https://api.subspace.com`
  * Version: Example: `v1`
  * The API Endpoint and any parameters: `accelerators/acc_NDA3MUI5QzUtOTY4MC00Nz` where `acc_NDA3MUI5QzUtOTY4MC00Nz` is a valid accelerator ID
  * Accelerator ids are always of the format `acc_NDA3MUI5QzUtOTY4MC00Nz`, with a \"acc_\" prefix followed by 22 characters.
  * Project ids are always of the format `prj_00Iaqxjo71vNL1uLKKo5Kn`, with a \"prj_\" prefix followed by 22 characters.
  * Token header: All REST requests require a valid JWT Bearer token which should be added as an “Authorization” header to the request:
      
      `Authorization: Bearer YOUR_TOKEN_HERE`
  
## Authorization header example

If your API token was “my_api_token”, you would add...

    Authorization: Bearer my_api_token
    
...to the header.

## Command line examples

To list your current open packet_accelerators using the token “my_api_token”:

    curl -H “Authorization: Bearer my_api_token” https://api.subspace.com/v1/accelerators
    
Alternately, to get the details of a specific accelerator whose id is 'abcd-ef01-2345':

    curl -H “Authorization: Bearer my_api_token” https://api.subspace.com/v1/accelerators/abcd-ef01-2345

# API Versioning

Subspace will release new versions when we make backwards-incompatible changes to the API. We will give advance notice before releasing a new version or retiring an old version.

Backwards compatible changes:
  * Adding new response attributes
  * Adding new endpoints
  * Adding new methods to an existing endpoint
  * Adding new query string parameters
  * Adding new path parameters
  * Adding new webhook events
  * Adding new streaming endpoints
  * Changing the order of existing response attributes
  
Versions are added to the base url, for example:
  * `https://api.subspace.com/v1`

Current Version is **v1:** `https://api.subspace.com/v1`


This Python package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: 1.0
- Package version: 1.0.1
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
        api_response = api_instance.accelerator_service_create(body, idempotency_key=idempotency_key)
        pprint(api_response)
    except subspace_openapi_client.ApiException as e:
        print("Exception when calling AcceleratorServiceApi->accelerator_service_create: %s\n" % e)
```

## Documentation for API Endpoints

All URIs are relative to *https://api.subspace.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AcceleratorServiceApi* | [**accelerator_service_create**](docs/AcceleratorServiceApi.md#accelerator_service_create) | **POST** /v1/accelerators | 
*AcceleratorServiceApi* | [**accelerator_service_delete**](docs/AcceleratorServiceApi.md#accelerator_service_delete) | **DELETE** /v1/accelerators/{id} | 
*AcceleratorServiceApi* | [**accelerator_service_get**](docs/AcceleratorServiceApi.md#accelerator_service_get) | **GET** /v1/accelerators/{id} | 
*AcceleratorServiceApi* | [**accelerator_service_list**](docs/AcceleratorServiceApi.md#accelerator_service_list) | **GET** /v1/accelerators | 
*AcceleratorServiceApi* | [**accelerator_service_update**](docs/AcceleratorServiceApi.md#accelerator_service_update) | **PUT** /v1/accelerators/{id} | 
*ProjectServiceApi* | [**project_service_create**](docs/ProjectServiceApi.md#project_service_create) | **POST** /v1/projects | 
*ProjectServiceApi* | [**project_service_get**](docs/ProjectServiceApi.md#project_service_get) | **GET** /v1/projects/{id} | 
*ProjectServiceApi* | [**project_service_list**](docs/ProjectServiceApi.md#project_service_list) | **GET** /v1/projects | 
*ProjectServiceApi* | [**project_service_update**](docs/ProjectServiceApi.md#project_service_update) | **PUT** /v1/projects/{id} | 
*SessionServiceApi* | [**session_service_list**](docs/SessionServiceApi.md#session_service_list) | **GET** /v1/accelerators/{accelerator_id}/sessions | 
*SipTeleportServiceApi* | [**sip_teleport_service_create**](docs/SipTeleportServiceApi.md#sip_teleport_service_create) | **POST** /v1/sip-teleports | 
*SipTeleportServiceApi* | [**sip_teleport_service_delete**](docs/SipTeleportServiceApi.md#sip_teleport_service_delete) | **DELETE** /v1/sip-teleports/{id} | 
*SipTeleportServiceApi* | [**sip_teleport_service_get**](docs/SipTeleportServiceApi.md#sip_teleport_service_get) | **GET** /v1/sip-teleports/{id} | 
*SipTeleportServiceApi* | [**sip_teleport_service_list**](docs/SipTeleportServiceApi.md#sip_teleport_service_list) | **GET** /v1/sip-teleports | 
*SipTeleportServiceApi* | [**sip_teleport_service_update**](docs/SipTeleportServiceApi.md#sip_teleport_service_update) | **PUT** /v1/sip-teleports/{id} | 


## Documentation For Models

 - [Body](docs/Body.md)
 - [Body1](docs/Body1.md)
 - [ProtobufAny](docs/ProtobufAny.md)
 - [V1Accelerator](docs/V1Accelerator.md)
 - [V1CreateSipTeleport](docs/V1CreateSipTeleport.md)
 - [V1ListAcceleratorsResponse](docs/V1ListAcceleratorsResponse.md)
 - [V1ListProjectsResponse](docs/V1ListProjectsResponse.md)
 - [V1ListSessionsResponse](docs/V1ListSessionsResponse.md)
 - [V1ListSipTeleportResponse](docs/V1ListSipTeleportResponse.md)
 - [V1NextPage](docs/V1NextPage.md)
 - [V1Project](docs/V1Project.md)
 - [V1Protocol](docs/V1Protocol.md)
 - [V1Session](docs/V1Session.md)
 - [V1SipTeleportResponse](docs/V1SipTeleportResponse.md)
 - [V1SipTeleportStatus](docs/V1SipTeleportStatus.md)
 - [V1TeleportAddresses](docs/V1TeleportAddresses.md)
 - [V1TransportType](docs/V1TransportType.md)
 - [V1UpdateSipTeleport](docs/V1UpdateSipTeleport.md)


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
 - **sessions:read**: allows reading details about PacketAccelerator sessions
 - **sessions:write**: allows administration of PacketAccelerator sessions
 - **projects:read**: allows reading details about projects
 - **projects:write**: allows administration of projects


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

