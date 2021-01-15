# How are WO Forms configured in FAMIS 360

Some customers have configured WO Forms in FAMIS 360.  These are additional attributes to collect about a request.  WO Forms are configured in FAMIS 360 as HTML forms and include print tokens.  Print tokens map to user defined fields on the new work request.

{% hint style="info" %}
WO Form configurations can be found in FAMIS 360 under the menu _Work Order Forms Format_.

A Work Order Form Format is associated with a Request Sub Type to determine on which new work requests it should show to the user.

Print tokens are identified on the WO Form wrapped in \*\* and are configured in _Application UDFs_ where Application = Logbook.
{% endhint %}

When creating a new work request the user will provide the standard information about the request, and then will be prompted with the WO Form information/prompts to respond to.

When the new work request is submitted to FAMIS 360, the standard information about the request is posted as well as the WO Form information.  The WO Form information is posted in the UDF object of the new work request.

