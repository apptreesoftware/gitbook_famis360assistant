# famis\_config

The famis\_config settings will control the following user experience in the assistant:

* Environment connection/credential details
* Create work request prompts
* Required field prompts
* View work request fields and editable field options

### Single option configurations:

| Config Data                | Options    | Example          | Notes                                                                                                                                                       |
| -------------------------- | ---------- | ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| url                        | url        |                  |                                                                                                                                                             |
| username                   | text       |                  |                                                                                                                                                             |
| password                   | text       |                  |                                                                                                                                                             |
| debug                      | true/false |                  |                                                                                                                                                             |
| active                     | true/false |                  |                                                                                                                                                             |
| createDate                 | datetime   |                  |                                                                                                                                                             |
| production                 | true/false |                  |                                                                                                                                                             |
| avatarUrl                  | url        |                  |                                                                                                                                                             |
| readableName               | text       |                  |                                                                                                                                                             |
| autoRetry                  | true/false |                  | (In FAMIS SDK) If call to FAMIS fails and autoretry is enabled then retry up to 3 times                                                                     |
| defaultWoSearchSize        |            |                  | When search by filter, limit the results returned.  If no value then default to 10                                                                          |
| selfRegistration           | true/false |                  |                                                                                                                                                             |
| enforceDomain              | true/false |                  | Used with self registration.  When enabled, then check email entered against domains of project custom domains                                              |
| forgotPasswordEnabled      | true/false |                  |                                                                                                                                                             |
| forgotPasswordText         | text       |                  |                                                                                                                                                             |
| forgotPasswordBelowText    | text       |                  |                                                                                                                                                             |
| famisNotificationTypes     | array      | push, sms, email | Set the same as [`famis_notification_types`](famis\_notification\_types.md) config.  Used for display in CW setup assistant                                 |
| notificationOnlyOnCreate   | true/false |                  | If true, then a push notification displays when WO created.  If false, then conversation is pushed to the user and in Active Conversations dashboard widget |
| watchers                   | true/false |                  |                                                                                                                                                             |
| descriptionRequired        | true/false |                  |                                                                                                                                                             |
| assetEnabled               | true/false |                  | Only enable if only full users will use the assistant                                                                                                       |
| cubeDisabled               | true/false |                  | Enable if FAMIS360 configuration requires room cube for guest users                                                                                         |
| assignEnabled              | true/false |                  | Only enable if only full users will use the assistant                                                                                                       |
| priorityEnabled            | true/false |                  | Used to override the FAMIS logbook configuration                                                                                                            |
| priorityRequired           | true/false |                  | Used to override the FAMIS logbook configuration                                                                                                            |
| displayDepartment          | true/false |                  | Enable if FAMIS360 configuration requires department for users                                                                                              |
| completionDateDisabled     | true/false |                  |                                                                                                                                                             |
| completionDateRequired     | true/false |                  | Citizens                                                                                                                                                    |
| externalCostCenterEnabled  | true/false |                  | Enable if FAMIS360 configuration requires external cost center                                                                                              |
| ccEmail                    | true/false |                  | Up to 5 cc email addresses can be added                                                                                                                     |
| changeRequestor            | true/false |                  | When enabled the requestor can be changed when create request                                                                                               |
| notifyRequestor            | true/false |                  |                                                                                                                                                             |
| trackingCode               | array      |                  | Name, Id                                                                                                                                                    |
| originCodeId               | number     |                  | Only used with Incoming Email Request feature                                                                                                               |
| attachmentsEnabled         | true/false |                  |                                                                                                                                                             |
| cancelEnabled              | true/false |                  |                                                                                                                                                             |
| showRequesterDetails       | true/false |                  |                                                                                                                                                             |
| commentsEnabled            | true/false |                  |                                                                                                                                                             |
| displayCommentUser         | true/false |                  | Determines if name is shown on the comments of the work request.  Same value set as in `commentSettings`                                                    |
| userContactEnabled         | true/false |                  | Restricts showing contact information (GCU)                                                                                                                 |
| watcherNotificationDefault | true/false |                  |                                                                                                                                                             |

### Array option configurations:

editableFields

| Config Data | Options    | Example | Notes |
| ----------- | ---------- | ------- | ----- |
| name        | true/false |         |       |
| department  | true/false |         |       |

commentSettings

| Config Data        | Options    | Example | Notes                                           |
| ------------------ | ---------- | ------- | ----------------------------------------------- |
| commentTypes       | array      |         | update, initial, closing, internal (true/false) |
| displayCommentUser | true/false |         |                                                 |
| onlyLastComment    | true/false |         |                                                 |
| displayAll         | true/false |         |                                                 |

propertySettings

| Config Data      | Options    | Example | Notes |
| ---------------- | ---------- | ------- | ----- |
| spaceSort        | text       | tab     |       |
| defaultOnly      | true/false |         |       |
| omitDefault      | true/false |         |       |
| floorEnabled     | true/false |         |       |
| floorSort        | text       | tab     |       |
| guestDefaultOnly | true/false |         | GCU   |

searchResultsText

| Config Data  | Options | Example     | Notes                      |
| ------------ | ------- | ----------- | -------------------------- |
| descText     | text    | Description |                            |
| typeText     | text    | Type        |                            |
| requestText  | text    | WO          | Prefix for work request ID |
| locationText | text    | Location    |                            |

requestTypeSettings

| Config Data       | Options                             | Example | Notes |
| ----------------- | ----------------------------------- | ------- | ----- |
| sortBy            | text                                | tab     |       |
| displayExternalId | true/false                          |         |       |
| requestSubType    | sortBy - text; enabled - true/false |         |       |

selfRegistrationDefaults

| Config Data      | Options    | Example | Notes |
| ---------------- | ---------- | ------- | ----- |
| loginHelp        | text       |         |       |
| firstName        | text       |         |       |
| lastName         | text       |         |       |
| title            | text       |         |       |
| companyId        | number     |         |       |
| companyName      | text       |         |       |
| addr1            | text       |         |       |
| city             | text       |         |       |
| stateId          | number     |         |       |
| stateName        | text       |         |       |
| zip              | text       |         |       |
| countryId        | number     |         |       |
| countryName      | text       |         |       |
| busPhone         | text       |         |       |
| type             | number     |         |       |
| typeName         | text       |         |       |
| unnamedGuestFlag | true/false |         |       |
| profileId        | number     |         |       |
| profileName      | text       |         |       |
| profileFlag      | boolean    |         |       |
|                  |            |         |       |
