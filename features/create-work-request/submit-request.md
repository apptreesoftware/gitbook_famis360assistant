# Submit Request

When a new work request is ready to submit to FAMIS 360, the following actions will need to occur:

1. Add conversation response to AT\_CONVERSATIONS
2. Trigger AT\_TASK that will call a task that will POST work request details to the FAMIS 360 API `WorkOrders`.  The response from this will contain the new work request ID
3. Trigger AT\_TASK that will push a conversation to the user notifying them of the new work request that was created.

### FAMIS 360 WorkOrder POST Details

{% api-method method="post" host="https://<customerenvironmenturl>/apis/360facility/v1/workorders" path="" %}
{% api-method-summary %}
WorkOrders
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="" type="string" required=false %}

{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```

```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

### Notification of New Work Request

A new conversation thread will be pushed to the user who created the work request to notify them the work request has been created, provide the request ID, and display a summary of the request details.

#### Title:  New work request XXXX has been created

#### SubTitle will be a markdown table containing the following details about the work request

* Statement of Work
* Request Type
* Request Sub Type
* Property / Floor / Space
* Asset \(only display if user is Full User\)
* Crew / Assigned To \(only display if user is Full User\)
* Create Date
* Requested Completion Date
* Status

When the user selects the new work request conversation, then redisplay the request details from the subtitle.

The conversation should then be marked complete.

