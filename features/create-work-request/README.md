# Create Work Request

FAMIS 360 allows users to create new work requests.  Depending on the user's permissions will determine what attributes they can enter for the new work request, as well as what list values they can select from.

Users will be prompted to enter the following standard information about the work request within the conversation.

### Select Location

| Order | Message | Prompt Options | List Information | API | Additional Information |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 1 | Your default location is &lt;PROPERTY NAME&gt; . Do you want to proceed with this? | Yes; No |  | `UserPropertyAssociation` | &lt;PROPERTY NAME&gt; represents the default property from the user security |
| 1.1 | Select a property | \(list\) | List of all available properties for the user. The list contains all properties the user is associated with, as well as any properties for the region\(s\) the user is associated with. Only display active properties. | `UserPropertyAssociation;  UserRegionAssociations; PropertyRegionAssociations` | If the user responds "No" to \#1.  Display the property name in ascending order |
| 2 | Select a floor | &lt;First list item floor&gt;; Select a different floor | List of all active floors for the property selected.  "&lt;First list item floor&gt;" prompt option will display the first list item based on tab order.  The "Select a different floor" will display a full list of floors for the property for the user to select from | `Floors` | If the user responds "Yes" to \#1.  If the property only has one floor then do not display this message prompt and set this floor as the response value.  Display the floor name in ascending order |
| 3 | Select a space | &lt;First list item space&gt;; Select a different space | List of all active spaces for the property/floor selected.  "&lt;First list item space&gt;" prompt option will display the first list item based on tab order.  The "Select a different space" will display a full list of the spaces for the property/floor for the user to select from | `Spaces` | If the property only has one space then do not display this message prompt and set this space as the response value.  Display the space name in ascending order |

{% hint style="info" %}
Some customers only have FAMIS 360 configured for Property & Space \(not Floor\).  The conversation should be flexible based on the customer's configuration options.
{% endhint %}

### Select Activity Group

| Order | Message | Prompt Options | List Information | API | Additional Information |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 4 | Please select one of the following that best describes your request | \(list\) | List of activity groups the user has access to | `UserActivityGroupAssociations` | Display the activity group name in ascending order |

### Select Request Type/Sub Type

| Order | Message | Prompt Options | List Information | API | Additional Information |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 5 | Select a request type | \(list\) | List of active request types for the activity group selected | `RequestTypeActivityGroupAssociations; RequestTypes` | Display the request type name in ascending order |
| 6 | Select a request sub type | \(list\) | List of active request sub types for the request type selected | `RequestSubTypes` | Display the request sub type name in ascending order |

### WO Form / Custom Information

If the request sub type selected is associated with a WO Form, then the message prompts will display the custom information and prompts to the user to respond to.  These message prompts will vary.

For more information regarding how WO Forms are configured in FAMIS 360, [click here](how-are-wo-forms-configured-in-famis-360.md).

Details regarding these additional message prompts will be documented for each customer assistant conversation request.  Refer to the AppTree ticket for more information.

### Verify Contact Information

| Order | Message | Prompt Options | List Information | API | Additional Information |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 7 | Please verify your contact information |  |  |  |  |
| 8 | &lt;markdown displaying user's first name, last name, phone, email, and department&gt; | Update contact information; Verified |  | `Users` | Customers will configure FAMIS360 to include/require phone, email, department.  These attributes will need to be validated if required and null before proceeding to the next message prompt |

To simplify the user experience, display the user's current contact information in a markdown display, but allow the user to update the information using a modal rather than within the conversation.

### Additional Details

| Order | Message | Prompt Options | List Information | API | Additional Information |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 9 | Please include additional details regarding your request | Select an asset; Pre-assign the work request; Select a priority; Add additional comments regarding the request; Set a requested completion date; Add attachments; I'm ready to submit this request |  |  | Only display prompt options "Select an asset" and "Pre-assign the work request" if the user is a Full User based on their user security settings. |
| 10.1 | Select the asset this work request pertains to | \(list\) | List of active assets for the property/floor/space selected | `Assets` | If the user responds "Select an asset" to \#9.  The user should be permitted to search a list of assets or scan a barcode.  Display the asset name and number in ascending order by number.  The value associated with the barcode scan will be "BarcodeNumber" |
| 10.2 | Would you like to pre-assign this work request to a crew, user or both | Crew; User; Both |  |  | If the user responds "Pre-assign the work request" to \#9. Only display this prompt option if the customer is using Crews in FAMIS360, else go to \#10.2.2  |
| 10.2.1 | Select a crew to assign to this work request | \(list\) | List of all active crews associated with the user | `CrewUserAssociations` | If the user responds "Crew" or "Both" to \#10.2.  Display the crew name in ascending order |
| 10.2.2 | Select a user to assign to this work request | \(list\) | List of all active full user accounts that have access to the selected activity group and allow assignment = Yes | `Users; UserActivityGroupAssociations` | If the user responds "User" or "Both" to \#10.2.  Display the user's lastname, firstname in ascending order |
| 10.3 | Enter additional comments regarding your work request |  |  |  | If the user responds "Add additional comments regarding the request" to \#9.  The user will be prompted with a text prompt.   |
| 10.4 | Select a requested completion date |  |  |  | If the user responds "Set a requested completion date" to \#9.  The user will be prompted with a date picker |
| 10.5 | Select a priority | \(list\) | List of active priorities.  | RequestPriorities; Properties.RequestPriorityListId; RequestPriorityLists  | If the user responds "Select a priority" to \#9. Display priority name in ascending order.  If the property selected is associated with a priority list, then display those priority list values otherwise display all priorities |
| 10.6 | Add attachments |  |  |  | If the user responds "Add attachments" to \#9.  The user can add as many attachments as they would like |
| 11 | Thank you for submitting a work request for  &lt;REQUEST TYPE&gt;/&lt;REQUEST SUB TYPE&gt; in location &lt;PROPERTY&gt;/&lt;FLOOR&gt;/&lt;SPACE&gt;. We will notify you when the work request is created and provide you with the new work request ID for your reference. |  |  |  | If the user responds "I'm ready to submit this request" to \#9.  Mark the conversation complete.  Refer to the [Submit Request](submit-request.md) section for details on how to create the work request and related conversations |

{% hint style="info" %}
The prompt options presented in \#9 are meant for the user to enter whatever additional details are needed for their new work request.  These are all optional details.  When a user selects one of the prompt options, they should be returned back to the full list of prompt options in \#7 to select another option.  Once the user selects the option to submit the request is when they will finally exit the prompt options in \#9 and move on in the conversation.
{% endhint %}

