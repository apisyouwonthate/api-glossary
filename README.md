# OpenAPI Glossary

To avoid confusion in the creation of educational material, tooling, and other content, having a shared vocabulary is important. A lot of people in the OpenAPI community call a lot of things a lot of different things, so let's take a swing at unification here.

## API

Tee general definition "Application Program Interface" can mean a lot of things, with different types of interface. OpenAPI is specifically talking about HTTP-based APIs, which in general is anything REST, RESTish, and many generic types of RPC. 

## API-First

When APIs first started getting popular, a lot of companies started flopping them out as a marketing ploy. These APIs were generally not particularly useful, rarely performant, and frustrating to work with.

"API First" is a concept that teams should build the APIs first, and make them something they would want to work with, therefore solving useability issues, performance issues, etc. and supposedly creating a better experience for their customers.

## API Description

Alias include: "API definition", "API contract".

An API Description is meta-data about an API, explaining what endpoints, resources, HTTP methods, headers, query parameters, etc. exist. 

Descriptions are written in a particular "API Description Format" (e.g.: OpenAPI, JSON Schema, RAML, WSDL, etc.) and will usually be contained in an "API Description Document" (e.g.: `openapi.yaml`, `schemas/payment.json`) unless the authors decided to use annotations instead.

## API Design

Planning an API specifically using API Descriptions, or a tool which generates / exports API descriptions. When done before coding begins, it is known as API Design First, which is conceptually different to [API First](#API-First) but not mutually exclusive. 

More on [API Design First vs Code First](https://www.apisyouwonthate.com/blog/api-design-first-vs-code-first/).

## API Specification

In the past the term API Specification was one of many terms to describe what most major tooling vendors call an [API Description Document](#API-Description-Document). It was the file that users would write to describe _their_ API.

Ask 100 people and you will get 100 answers, but consensus is forming around API Specifications being an umbrella term for various Specifications involve with API development, and more specific categories exist within the umbrella term.

Message Formats like JSON-API, HAL, Siren, etc. all have a specification.
Data Formats like JSON, YAML, etc all have a specification.

Transfer Protocols like SPDY, HTTP/2, HTTP/3, etc have a specification.

Authentication Strategies like OAuth 2, OpenID, etc all have a specification.

Seeing as there as so many types of API specification floating around, to disambiguate its best to just avoid the term and use one of the more specific categories, or if talking about your own `openapi.yaml` just call it the description document.

## Bundle

Aliases include: "external inlining".

Bundling pulls in external $refs from different files, or URLs, and puts them into the `components` object. 

This is done to create a single OpenAPI file, which is easier to share, especially with tooling that does not support resolving external files. If tooling does not support $ref at all, then an alternative to bundling is required: [dereferencing](#dereference).

## Callbacks

## Code Generation

## Contract Testing

Confirming that an API is accepting and outputting what it says it is can take many forms. Most commonly, when you hear the term Contract Testing in relation to OpenAPI, people are talking about producer contract testing. This means the API development team (or some test/QA team nearby) have implemented a test suite that will [take an API description and compare it to the actual data](https://apisyouwonthate.com/blog/writing-documentation-via-contract-testing/). 

Conceptually contract testing is the same thing as [data validation](#data-validation), but done for different purposes at different parts of the life-cycle. The same tools could be used under the hood.

There is also client-side contract testing, where you write out the contract in a client test suite then make calls to the API to see if it matches.

## Data Instance

## Data Validation

## Dereference

Aliases include: "dereferencing", "internal inlining" or "transclusion".

All $refs and replaced with their values a'la copy & paste.

No more $ref’s exist in the file/object representation. If you have 10 operations referencing the same model 10 times, you now have 10 different models.

## Documentation

## Links

## Mocking

A fake server that takes a description document as input, then routes incoming HTTP requests to example responses or dynamically generates examples. 

_A list of mock servers is available on [OpenAPI.Tools](https://openapi.tools/#mock-servers)._

## OAS

This is just shorthand for the OpenAPI Specification, which is just [Markdown files on the internet](https://github.com/OAI/OpenAPI-Specification/tree/master/versions) defining how each version of OpenAPI should work.

## OpenAPI

The new name of the [API Description](#API-Description) Format, which is defined in an [API Specification](#API-Specification). It used to be called [Swagger](#Swagger).

## The OpenAPI Initiative

The [OpenAPI Initiative](https://www.openapis.org) (OAI) are the group in control of the development of the OpenAPI Specification ([OAS](#OAS)).

## Open API

An open API is a public API.

When referring to the [OpenAPI Specification](#OAS), community or the [OpenAPI Initiative](#The-OpenAPI-Initiative), there is no space in "OpenAPI".

## Reference Documentation

## Reference

A JSON Reference, which can be a file, URI, or reference an id. They live inside the Reference Object, with the key `$ref`.

## Resolve

Looking for the value found at the end of a `$ref`, but no changes are made to the file or object being resolved. 

## Runtime Validation

## Schema

## Schema Validation

## SDK

## Server-side Validation

## Swagger

Historically, "Swagger" was the original name of OpenAPI Specification (OAS). It was called Swagger when it was released in 2011, and when SmartBear aquired Swagger they kept the name for a while, and made a bunch of tools with the name Swagger in it. Swagger Editor, Swagger Inspector, SwaggerHub, etc. 

Once the Swagger specification was given to [Open API Initiative](#Open-API-Initiative) in 2016, the name was changed to OpenAPI. 

Now, the word "Swagger" is just part of the SwaggerHub brand of tooling. The specification is "OpenAPI" (not OpenAPI/Swagger).
