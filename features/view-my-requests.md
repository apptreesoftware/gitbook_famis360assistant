# View My Requests

A user can view their open work requests as well as search for any work request they are the requestor for.

### View My Open Requests

Display a list of work requests that are requested by the user and have an open type of status.

#### API: WorkOrders

* WorkOrders.RequestorId = User ID
* WorkOrders.StatusId = RequestStatuses.Id where OpenStatusFlag = true

The attributes that should be displayed in a table include the following:

* ID
* Location \(property name / floor name / space name\)
* Request Type / SubType
* Status
* Priority
* Statement of Work

The user should then be presented with options to **Update a Work Request** or **Go Back**.

The **Update a Work Request** option will display a list of all the open work requests returned \(ID only\) and allow the user to select a value.  When the work request is selected, then the user is presented with additional options they can do.

* View/Add Attachments
* Add Comment \(general comment\)
* Cancel Request
* Go Back \(return to list of work requests\)

The **Go Back** option will return the user to the "View My Requests" main menu.

### Find Requests

Allow a user to search for work requests using filters.

#### API: WorkOrders

RequestorId will always equal the user's ID.

Additional filters the user can select:

* ID
* Property \(list of properties the user has access to\)
* Status
* Request Type

The results should display similar to the display in View My Open Requests.

Results should be displayed using &lt;Previous / Next&gt; paging functionality.  Display 16 work request results for each paging display.

If there are any work requests in the results that have an open type of status, then display the prompt options **Update a Work Request** or **Go Back**.  Only those work requests with an open type of status will be listed for selection when the user selects **Update a Work Request**.

If there are no work requests in the results with an open type of status, then return the user to the "View My Requests" main menu.

### 

