# api-handbook

The echelon.solutions API handbook describing best practices for API development and management.

<a href="https://echelon.solutions"><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAXAAAAChCAMAAADp0hQzAAAC0FBMVEUAAAA7yrU+yrQ9yrQ9ybNA0LA9ybM9ybRAyLA9ybQ+ybQ9ybM8yLQ+yrM9ybM9yrM+yrQ+yrM+ybQ+yrI+yrM9yrM9yrQ9ybM+ybM/yLQ+yrQ+ybI9y7N2cmp2cmp3c2pubm50dGt2cmt3cmt5bGx1cml3cml4cWuAZ2d2dmN2c2t2cmt3cmt2cmp3c2t3cmp1cW1VVVVzc2d2cmp2cmp2c2t3cmp2cmp3cmp3d24AAABwcHB3cmx3c2t3c2p2c2p3c2p2cmp4cGh3cmt3c2p3c2t3cmp3dGqAgFV5c2x3cmt2cmt3cmt1cmx2c2t2c2pycmh2c2t2cmt0dGh2cmt3c2p2cmp1cWl3d2Z3cmt3c2p2c2t1dW50dGt2cmt3c2t1c2t2cmt2c2p2dGt1cGx2c2t4dGl2cmt2c2t2c2t2cWx1cmx3cmp3c2p6c213c2t4cWl2c2p0dG17cWZ3c2x2cmt5dGp2cmt3cGpycnJ2cmp3cmp2c2p4dGt4eGl2c2pzc2p3dGt4cWp3cmt3cmt1dWt2c2p3cmp2cGl3cmt2cmp3c2t3c2p6bm53cWl3c2p2dmx2cmp3c2p0dGl3c2t1cGt2cmp2c2tnZ2d3cmp2c2t2cmp2cmp2cmt2cWlycmR2dmh2c2t3dGl2c2p3cmp2c2t2cmt4c2l2c2t2c2t2cmt2c2t2c2p4cmp1dWp3cmt3c2t2c2p3c2p3cmx3c2x3cmp3c2p3c2t3cmp5cmt2cmp4cm13cmt2dGt3b2Z3c2t3cmt2cmt3c2t2c2p2cmt2c2t3cmt3cmt3c2qAgIB3c2p0dHR3c2t2cmt3dGp3cml2c2p3cmx3cmp2c2t2cmp3cmp2c2p4c2l3cmp3cmp3c2t3cmh2cWx3cWt2cmp2c2x2cmt0dGl3c2p3cmt3cmt2c2p3c2pubm52c2p3cmt2c2p2cmt3c2t3cmp2cmt3c2sIFnGoAAAA8HRSTlMAMF/f/xB/7yCfwKBAv/CQgOBwYNCPsFDPb69PP37/xA438KgTVVpPCg1bvev95J87AxRqwfXeq2McARAtfcvorj8g0+/85UsGJm624lPhpxt6jSpz8dlED5n4ySMftO1glOxdOd1CdZ5ZNFG8OiiVItshGUXKNc4pCb/0qT4R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" /></a>

- [contact@echelon.solutions](mailto:contact@echelon.solutions)
- [https://echelon.solutions](https://echelon.solutions)

Please submit an issue to ask a question or start a community discussion around best practices. Open a pull request to have your additions or edits reviewed.

This document can also be viewed at the [GitHub Pages site](https://echelon-solutions.github.io/api-handbook/).

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

```
"id": "01234567-89ab-cdef-0123-456789abcdef"
```

Resources should also include `created_at` and `updated_at` timestamps by default, where applicable.

### Caching

To support client caching, be sure to include an `ETag` header in all responses that identifies the version of the returned resource. Clients can check for staleness by supplying the `ETag` header value in the `If-None-Match` header in subsequent requests.

### DateTime Format

Accept and return times in UTC only, specifically in `ISO8601` format. For example:

```
"updated_at": "2012-01-01T12:00:00Z"
```

### Relationships

Nest foreign key relationships by serializing the foreign object rather than including an identifier field. This approach allows adding more information about the related resource without having to change the structure of the top-level response.

For example, this is preferred:

```json
{
  "title": "How to document an API",
  "author": {
    "id": "01234567",
    "name": "John Doe"
  }
}
```

This is not:

```json
{
  "title": "How to document an API",
  "authorId": "01234567"
}
```

## Versioning

### Accepts Header

Use the `Accepts` header with a custom content type. This has the added benefit of pegging a specific request object version as well as an API version. For example:

```
application/vnd.blog.post+json; version=2
```

### Request URI

Alternatively, rather than using the [Accepts Header](#accepts-header) approach, the version of the API appears in the URL. For example:

```
https://api.example.com/v1/posts
```

## Inspiration and Thanks

Much of the content of this API handbook can be attributed to a collection of fine resources. Here they are mentioned below for further and supplemental reading:

- [UC Berkeley Enterprise Integration Services](http://integration-services.berkeley.edu/using-apis/api-best-practices)
- [Interagent Heroku Platform HTTP API Design Guide](https://github.com/interagent/http-api-design)
