# Submit Request

When a new work request is ready to submit to FAMIS 360, the following actions will need to occur:

1. Add conversation response to AT\_CONVERSATIONS
2. Trigger AT\_TASK that will call a task that will POST work request details to the FAMIS 360 API `WorkOrders`.  The response from this will contain the new work request ID
3. Trigger AT\_TASK that will push a conversation to the user notifying them of the new work request that was created.

### FAMIS 360 WorkOrder POST Details

### Notification of New Work Request

#### Title:  New work request XXXX has been created

#### SubTitle will be a markdown table containing the following details about the work request

* Statement of Work
* Request Type
* Request Sub Type
* Property / Floor / Space
* Asset
* Assigned To

Create an AT\_TASK trigger that will call the FAMIS 360 API to create the new work request. The response will contain the new work request ID. When the task has completed, then push a conversation to the user with the following. Title: New work request XXXX has been created Subtitle: markdown table that displays the request details including statement of work, request type, sub type, property, space, asset, assigned to, requested completion date, status, create date

When the user selects the new work request conversation, then redisplay the request details from the subtitle. The conversation should then be marked complete.

