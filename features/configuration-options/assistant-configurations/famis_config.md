# famis\_config

The famis\_config settings will control the following user experience in the assistant:

* Environment connection/credential details
* Create work request prompts
* Required field prompts
* View work request fields and editable field options

### Single option configurations:

{% hint style="warning" %}
Origination code/tracking code?
{% endhint %}

| Config Data                | Options    | Example          | Notes              |
| -------------------------- | ---------- | ---------------- | ------------------ |
| url                        | url        |                  |                    |
| username                   | text       |                  |                    |
| password                   | text       |                  |                    |
| debug                      | true/false |                  |                    |
| active                     | true/false |                  |                    |
| createDate                 | datetime   |                  |                    |
| production                 | true/false |                  |                    |
| avatarUrl                  | url        |                  |                    |
| readableName               | text       |                  |                    |
| **famisNotificationTypes** | array      | push, sms, email |                    |
| notificationOnlyOnCreate   | true/false |                  |                    |
| watchers                   | true/false |                  |                    |
| descriptionRequired        | true/false |                  |                    |
| assetEnabled               | true/false |                  |                    |
| cubeDisabled               | true/false |                  |                    |
| assignEnabled              | true/false |                  |                    |
| priorityEnabled            | true/false |                  |                    |
| priorityRequired           | true/false |                  | accruent\_360demom |
| displayDepartment          | true/false |                  |                    |
| completionDateDisabled     | true/false |                  |                    |
| completionDateRequired     | true/false |                  | Citizens           |
| attachmentsEnabled         | true/false |                  |                    |
| cancelEnabled              | true/false |                  |                    |
| showRequesterDetails       | true/false |                  |                    |
| commentsEnabled            | true/false |                  |                    |
| **displayCommentUser**     | true/false |                  |                    |
| userContactEnabled         | true/false |                  |                    |
| watcherNotificationDefault | true/false |                  |                    |

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
| guestDefaultOnly | true/false |         | GCU   |

searchResultsText

| Config Data  | Options | Example     | Notes |
| ------------ | ------- | ----------- | ----- |
| descText     | text    | Description |       |
| typeText     | text    | Type        |       |
| requestText  | text    |             |       |
| locationText | text    | Location    |       |

requestTypeSettings

| Config Data    | Options                             | Example | Notes |
| -------------- | ----------------------------------- | ------- | ----- |
| sortBy         | text                                | tab     |       |
| requestSubType | sortBy - text; enabled - true/false |         |       |

selfRegistrationDefaults

| Config Data | Options | Example | Notes |
| ----------- | ------- | ------- | ----- |
| loginHelp   | text    |         |       |
