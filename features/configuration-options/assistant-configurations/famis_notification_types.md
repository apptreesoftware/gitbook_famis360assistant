# famis\_notification\_types

This configuration indicates the type of notification methods which the user will receive alerts.  Options are:

* push
* sms
* email

The notification method **`push`** is the most common one configured for projects

On creation of the work request, the task that creates the WO in FAMIS360 also pushes a notification to the assistant letting them know the new work request has been created.  If email or sms notification type is enabled, then this created WO notification will be sent via these methods as well.

No notifications are sent when the work request is updated/edited.
