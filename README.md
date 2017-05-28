# api-handbook

The echelon.solutions API handbook describing best practices for API development and management.

- [contact@echelon.solutions](mailto:contact@echelon.solutions)
- [www.echelon.solutions](www.echelon.solutions)

Please submit an issue to ask a question or start a community discussion around best practices. Open a pull request to have your additions or edits reviewed.

**Contents**
- [Security](#security)
	- [Protocol](#protocol)
    - [Authentication](#authentication)
    - [Authorization](#authorization)
- [IO](#io)
	- [Status Codes](#status-codes)
    - [Resource Identifiers](#resource-identifiers)
    - [DateTime Format](#datetime-format)

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

### Resource Identifiers

Each resource should have an `id` attribute. Use only globally unique identifiers that are unique across instances of the service and across resources of the service. This can be accomplished using UUIDs, for example:

```json
{
	"id": "01234567-89ab-cdef-0123-456789abcdef"
}
```

Resources should also include `created_at` and `updated_at` timestamps by default, where applicable.

### DateTime Format

Accept and return times in UTC only, specifically in `ISO8601` format. For example:

```json
{
	"updated_at": "2012-01-01T12:00:00Z"
}
```




