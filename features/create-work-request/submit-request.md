# Submit Request

When a new work request is ready to submit to FAMIS 360, the following actions will need to occur:

1. Add conversation response to AT\_CONVERSATIONS
2. Trigger AT\_TASK that will call a task that will POST work request details to the FAMIS 360 API `WorkOrders`.  The response from this will contain the new work request ID
3. Trigger AT\_TASK that will push a conversation to the user notifying them of the new work request that was created.

### FAMIS 360 WorkOrder POST Details

{% api-method method="post" host="https://<CustomerEnvironmentURL>/apis/360facility/v1/workorders" path="" %}
{% api-method-summary %}
WorkOrders
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="RequestorLastName" type="string" required=false %}
User's last name
{% endapi-method-parameter %}

{% api-method-parameter name="RequestorFirstName" type="string" required=false %}
User's first name
{% endapi-method-parameter %}

{% api-method-parameter name="RequestorEmail" type="string" required=false %}
User's email
{% endapi-method-parameter %}

{% api-method-parameter name="RequestorPhone" type="string" required=false %}
User's phone
{% endapi-method-parameter %}

{% api-method-parameter name="DepartmentId" type="integer" required=false %}
User's department
{% endapi-method-parameter %}

{% api-method-parameter name="SpaceId" type="integer" required=false %}
Space prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="RequestTypeId" type="integer" required=false %}
Request Type prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="RequestSubTypeId" type="integer" required=false %}
Request SubType prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="StatementOfWork" type="string" required=false %}
Additional comments prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="AssetId" type="integer" required=false %}
Asset prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="CrewId" type="integer" required=false %}
Crew prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="AssignedToId" type="integer" required=false %}
Assigned To prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="RequestPriorityId" type="integer" required=false %}
Priority prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="RequestedCompletionDate" type="string" required=false %}
Requested completion date prompt response
{% endapi-method-parameter %}

{% api-method-parameter name="NotifyRequestorFlag" type="boolean" required=false %}
False
{% endapi-method-parameter %}

{% api-method-parameter name="Udfs" type="array" required=false %}
If work request has WO Form/Custom Information, then include prompt responses in the appropriate UDF
{% endapi-method-parameter %}

{% api-method-parameter name="Attachments" type="array" required=false %}

{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}

{% endapi-method-response-example-description %}

```
--Refer to Accruent API documentation for details regarding API response
--New work request ID will be included in the response
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

If any of the API request body attributes do not have a value, then they should not be included in the POST request.

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

Display message prompt equivalent to the conversation main menu so the user can perform an additional action if they want.

The Title/Subtitle should be changed to those used when a user first starts a conversation \(refer to [Features](../) for details\).

