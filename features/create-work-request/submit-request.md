# Submit Request

When a new work request is ready to submit to FAMIS 360, the following actions will need to occur:

1. Add conversation response to AT\_CONVERSATIONS
2. Trigger AT\_TASK that will call a task that will POST work request details to the FAMIS 360 API `WorkOrders`.  The response from this will contain the new work request ID
3. Trigger AT\_TASK that will push a conversation to the user notifying them of the new work request that was created.

### FAMIS 360 WorkOrder POST Details

{% swagger baseUrl="https://<CustomerEnvironmentURL>/apis/360facility/v1/workorders" path="" method="post" summary="WorkOrders" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="body" name="RequestorLastName" type="string" %}
User's last name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RequestorFirstName" type="string" %}
User's first name
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RequestorEmail" type="string" %}
User's email
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RequestorPhone" type="string" %}
User's phone
{% endswagger-parameter %}

{% swagger-parameter in="body" name="DepartmentId" type="integer" %}
User's department
{% endswagger-parameter %}

{% swagger-parameter in="body" name="SpaceId" type="integer" %}
Space prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RequestTypeId" type="integer" %}
Request Type prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RequestSubTypeId" type="integer" %}
Request SubType prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="StatementOfWork" type="string" %}
Additional comments prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="AssetId" type="integer" %}
Asset prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="CrewId" type="integer" %}
Crew prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="AssignedToId" type="integer" %}
Assigned To prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RequestPriorityId" type="integer" %}
Priority prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="RequestedCompletionDate" type="string" %}
Requested completion date prompt response
{% endswagger-parameter %}

{% swagger-parameter in="body" name="NotifyRequestorFlag" type="boolean" %}
False
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Udfs" type="array" %}
If work request has WO Form/Custom Information, then include prompt responses in the appropriate UDF
{% endswagger-parameter %}

{% swagger-parameter in="body" name="Attachments" type="array" %}

{% endswagger-parameter %}

{% swagger-response status="200" description="" %}
```
--Refer to Accruent API documentation for details regarding API response
--New work request ID will be included in the response
```
{% endswagger-response %}
{% endswagger %}

If any of the API request body attributes do not have a value, then they should not be included in the POST request.

### Notification of New Work Request

A new conversation thread will be pushed to the user who created the work request to notify them the work request has been created, provide the request ID, and display a summary of the request details.

#### Title:  New work request XXXX has been created

#### SubTitle will be a markdown table containing the following details about the work request

* Statement of Work
* Request Type
* Request Sub Type
* Property / Floor / Space
* Asset (only display if user is Full User)
* Crew / Assigned To (only display if user is Full User)
* Create Date
* Requested Completion Date
* Status

When the user selects the new work request conversation, then redisplay the request details from the subtitle.

Display message prompt equivalent to the conversation main menu so the user can perform an additional action if they want.

The Title/Subtitle should be changed to those used when a user first starts a conversation (refer to [Features](../) for details).
