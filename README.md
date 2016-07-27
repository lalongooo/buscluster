# Business Clúster API

This describes the resources that make up the official Business Clúster API. If you have any problems or requests please contact [support](mailto:adolfo.arreaga@5is.com.mx).

## Overview

1. [Schema](#schema).
2. [Parameters](#parameters).
3. [Root endpoint](#root-endpoint).
4. [HTTP Verbs](#http-verbs).
5. [Authentication](#authentication).

## Companies

1. [List companies](#list-companies).

### Schema

All API access is over HTTPS, and accessed from https://api.businesscluster.com.mx. All data is sent and received as JSON.

### Parameters

API methods take optional parameters. For GET requests, any parameters not specified as a segment in the path can be passed as an HTTP query string parameter:

`curl -i "https://api.businesscluster.com.mx/companies?type=platinum"`

### Root endpoint

All the calls to the API are accessed from this url:

`curl https://api.businesscluster.com.mx`

### HTTP Verbs

| Verb   | Description                                                                                                                                                                                                                                                                                            |
|--------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| HEAD   | Can be issued against any resource to get just the HTTP header info.                                                                                                                                                                                                                                   |
| GET    | Used for retrieving resources.                                                                                                                                                                                                                                                                         |
| POST   | Used for creating resources.                                                                                                                                                                                                                                                                           |
| PATCH  | Used for updating resources with partial JSON data. For instance, an Issue resource has title and body attributes. A PATCH request may accept one or more of the attributes to update the resource. PATCH is a relatively new and uncommon HTTP verb, so resource endpoints also accept POST requests. |
| PUT    | Used for replacing resources or collections. For PUT requests with no body attribute, be sure to set the Content-Length header to zero.                                                                                                                                                                |
| DELETE | Used for deleting resources.                                                                                                                                                                                                                                                                           |


### Authentication

To Be Defined

### List companies

List all the companies that are accessible to the authenticated user.

`GET /companies`

**Parameters**

| Name          | Type     | Desription                                                                                                                                                                                                 |
|---------------|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `type`        | `string` | Can be one of `platinum`, `all`. Default: `all`. **Important**: Here you can add all the filters on companies registered within Business Cluster, filters should be other than by `category`/`subcategory` |
| `category`    | `string` | Filters the companies that belong to the provided category.                                                                                                                                                |
| `subcategory` | `string` | List all the companies of the provided `subcategory`. **Important**: If `subcategory` is provided, `category` becomes a required parameter.                                                                |
