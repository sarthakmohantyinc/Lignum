---
description: >-
  Get resources with a simple RESTful API. Upload notes and homework with a
  simple POST request.
---

# API

{% api-method method="get" host="https://api.sarthakmohanty.me" path="/v1/get/resources/:key" %}
{% api-method-summary %}
Get Resources
{% endapi-method-summary %}

{% api-method-description %}
This endpoint responds with links to resources.
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="key" type="string" required=true %}
Search term to find the resource.
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is grabbing our resources.
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Resource successfully retrieved.
{% endapi-method-response-example-description %}

```
{
    "name": "Resource name",
    "subject": "Subject of resource",
    "icon": "fas fa-file",
    "link": "formatted like a link"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
Could not find a resource matching this query.
{% endapi-method-response-example-description %}

```
{
    "message": "Ain't no resource like that."
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="https://api.sarthakmohanty.me" path="/v1/post/resources/:key" %}
{% api-method-summary %}
Post Resources
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="key" type="string" required=true %}
s3 key where the link is supposed to be
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}

{% api-method-headers %}
{% api-method-parameter name="Authentication" type="string" required=true %}
Authentication token to track down who is grabbing our resources.
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="secured" type="boolean" required=false %}
True is resource should be secured. False if resource should be free.
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
Resource successfully uploaded.
{% endapi-method-response-example-description %}

```
{
    "message": "Successfully Uploaded"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=400 %}
{% api-method-response-example-description %}
Could not upload the resource.
{% endapi-method-response-example-description %}

```
{
    "message": "Failed to Upload"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

