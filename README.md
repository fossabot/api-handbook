# api-handbook

The echelon.solutions API handbook describing best practices for API development and management.

- [contact@echelon.solutions](mailto:contact@echelon.solutions)
- [www.echelon.solutions](www.echelon.solutions)

Please submit an issue to ask a question or start a community discussion around best practices. Open a pull request to have your additions or edits reviewed.

**Contents**
- [Introduction](#api-handbook)
- [Security](#security)
	- [Protocol](#protocol)
    - [Authentication](#authentication)
    - [Authorization](#authorization)
- [IO](#io)
	- [Status Codes](#status-codes)
    - [Errors](#errors)
    - [Resource Identifiers](#resource-identifiers)
    - [Caching](#caching)
    - [DateTime Format](#datetime-format)
    - [Relationships](#relationships)
- [Versioning](#versioning)
	- [Accepts Header](#accepts-header)
    - [Request URI](#request-uri)
- [Inspiration and Thanks](#inspiration-and-thanks)

## Security

### Protocol

TLS should be required for *all* endpoints, without exception.

### Authentication

Every REST API *must* at least accept basic authentication. Both protected and public resources should be marked and documented as such.

### Authorization

The REST APIs should not handle authorization. Authorization is a service layer concern that ensures that the *authenticated* client has the correct permissions to access the requested resource.

## IO

### Status Codes

Here is a document containing the [HTTP response code specification](https://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html). An appropriate HTTP status code should be returned for every response.

For successful responses, here is a general guideline:

- `200`: Request succeeded; appropriate for synchronous `GET`/`DELETE`/`PATCH` calls.
- `201`: Request succeeded; appropriate for synchronous `POST` calls that involve resource creation.
- `202`: Request accepted; appropriate for asynchronous `POST`/`DELETE`/`PATCH` calls.
- `206`: Request succeeded; appropriate for `GET` calls that return only a partial response.

### Errors

Always use a consistent error response structure. This response should at the very least include a machine-readable error `id` and a human readable error `message`. All error response scenarios should be included as part of the API documentation.

Preferably, also include a developer-readable `developerMessage` and a `url` directing the client to further documentation about the error and how to resolve it. For example:

`HTTP/1.1 429 Too Many Requests`

```json
{
	"id": "rate_limit",
    "message": "Maximum number of requests.",
   	"developerMessage": "This account reached the maximum API rate limit.",
    "url": "https://api.example.com/docs/rate-limits"
}
```

### Resource Identifiers

Each resource should have an `id` attribute. Use only globally unique identifiers that are unique across instances of the service and across resources of the service. This can be accomplished using UUIDs, for example:

`"id": "01234567-89ab-cdef-0123-456789abcdef"`

Resources should also include `created_at` and `updated_at` timestamps by default, where applicable.

### Caching

To support client caching, be sure to include an `ETag` header in all responses that identifies the version of the returned resource. Clients can check for staleness by supplying the `ETag` header value in the `If-None-Match` header in subsequent requests.

### DateTime Format

Accept and return times in UTC only, specifically in `ISO8601` format. For example:

`"updated_at": "2012-01-01T12:00:00Z"`

### Relationships

Nest foreign key relationships by serializing the foreign object rather than including an identifier field. This approach allows adding more information about the related resource without having to change the structure of the top-level response.

For example, this is preferred:

```json
{
	"title": "How to document an API"
    "author": {
    	"id": "01234567",
        "name": "John Doe"
    }
}
```

This is not:

```json
{
	"title": "How to document an API"
    "authorId": "01234567"
}
```

## Versioning

### Accepts Header

Use the `Accepts` header with a custom content type. This has the added benefit of pegging a specific request object version as well as an API version. For example:

`application/vnd.blog.post+json; version=2`

### Request URI

Alternatively, rather than using the [Accepts Header](#accepts-header) approach, the version of the API appears in the URL. For example:

`https://api.example.com/v1/posts`

## Inspiration and Thanks

Much of the content of this API handbook can be attributed to a collection of fine resources. Here they are mentioned below for further and supplemental reading:

- [UC Berkeley Enterprise Integration Services](http://integration-services.berkeley.edu/using-apis/api-best-practices)
- [Interagent Heroku Platform HTTP API Design Guide](https://github.com/interagent/http-api-design)
