# Configuration Options

There are many configuration options available for the FAMIS360 assistant to customize the user experience desired.  The following is a list of those options by the configuration group name.

### auth\_proxy\_branding

| Config Data     | Options | Example | Notes                                                                 |
| --------------- | ------- | ------- | --------------------------------------------------------------------- |
| logoUrl         | url     |         | Url to AppTree public image file.  This image shows on the login page |
| backgroundColor | text    |         | Hex code color of background that will show on the login page         |

### famis\_notification\_types

Indicates the type of notification methods which the user will receive alerts.  Options are:

* push
* sms
* email

The notification method **`push`** is the most common one configured for projects

{% hint style="warning" %}
What notifications are sent by the assistant?
{% endhint %}

### famis\_config

Single option configurations:

| Config Data                 | Options    | Example          | Notes    |
| --------------------------- | ---------- | ---------------- | -------- |
| url                         | url        |                  |          |
| debug                       | true/false |                  |          |
| active                      | true/false |                  |          |
| password                    | text       |                  |          |
| username                    | text       |                  |          |
| watchers                    | true/false |                  |          |
| avatarUrl                   | url        |                  |          |
| createDate                  | datetime   |                  |          |
| production                  | true/false |                  |          |
| assetEnabled                | true/false |                  |          |
| cubeDisabled                | true/false |                  |          |
| readableName                | text       |                  |          |
| assignEnabled               | true/false |                  |          |
| cancelEnabled               | true/false |                  |          |
| commentsEnabled             | true/false |                  |          |
| priorityEnabled             | true/false |                  |          |
| displayDepartment           | true/false |                  |          |
| attachmentsEnabled          | true/false |                  |          |
| **displayCommentUser**      | true/false |                  |          |
| userContactEnabled          | true/false |                  |          |
| completionDateDisabled      | true/false |                  |          |
| completionDateRequired      | true/false |                  | Citizens |
| **famiseNotificationTypes** | array      | push, sms, email |          |
| notificationOnlyOnCreate    | true/false |                  |          |
| watcherNotificationDefault  | true/false |                  |          |
| descriptionRequired         | true/false |                  |          |

Array option configurations:

editableFields

| Config Data | Options    | Example | Notes |
| ----------- | ---------- | ------- | ----- |
| name        | true/false |         |       |
| department  | true/false |         |       |

commentSettings

| Config Data        | Options                                                                                | Example | Notes |
| ------------------ | -------------------------------------------------------------------------------------- | ------- | ----- |
| commentTypes       | update - true/false; initial - true/false; closing - true/false; internal - true/false |         |       |
| displayCommentUser | true/false                                                                             |         |       |
| onlyLastComment    | true/false                                                                             |         |       |
| displayAll         | true/false                                                                             |         |       |

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

### dashboard\_config

Single option configurations:

| Config Data              | Options    | Example | Notes |
| ------------------------ | ---------- | ------- | ----- |
| helpText                 | text       |         |       |
| bannerImageUrl           | url        |         |       |
| stepFlowEnabled          | true/false |         |       |
| closedRequestSize        | number     |         |       |
| allRequestsEnabled       | true/false |         |       |
| openRefreshInterval      | number     | 30      |       |
| openRequestsEnabled      | true/false |         |       |
| closedRefreshInterval    | number     | 30      |       |
| closedRequestsEnabled    | true/false |         |       |
| watcherRefreshIntervale  | number     | 6000    |       |
| watcherRequestsEnabled   | true/false |         |       |
| closedRequestsWithinDays | number     | 60      |       |

Array option configurations:

searchRequests

| Config Data | Options | Example | Notes |
| ----------- | ------- | ------- | ----- |
| title       | text    |         |       |
| prompt      | text    |         |       |
| description | text    |         |       |

contactWidgetText

| Config Data | Options | Example | Notes |
| ----------- | ------- | ------- | ----- |
| email       |         |         |       |
| phone       |         |         |       |
| title       |         |         |       |
| details     |         |         |       |

namedGreetingOptions

| Config Data | Options    | Example | Notes |
| ----------- | ---------- | ------- | ----- |
| useFirst    | true/false |         |       |

openRequestsWidgetText

{% tabs %}
{% tab title="Config Data" %}


| Config Data | Options | Notes                                         |
| ----------- | ------- | --------------------------------------------- |
| widgetText  | array   | descText, typeText, requestText, locationText |
{% endtab %}

{% tab title="Example" %}
```
    "openRequestsWidgetText": {
        "widgetText": {
            "descText": "Description",
            "typeText": "Type",
            "requestText": "Work Request ",
            "locationText": "Location"
        }
    }
```
{% endtab %}
{% endtabs %}

closedRequestsWidgetText

{% tabs %}
{% tab title="Config Data" %}
| Config Data | Options | Notes                                         |
| ----------- | ------- | --------------------------------------------- |
| widgetText  | array   | descText, typeText, requestText, locationText |
{% endtab %}

{% tab title="Example" %}
```
    "closedRequestsWidgetText": {
        "widgetText": {
            "descText": "Description",
            "typeText": "Type",
            "requestText": "Work Request ",
            "locationText": "Location"
        }
    }
```
{% endtab %}
{% endtabs %}

requestTypeSubTypeWidget

| Config Data                | Options   | Example | Notes                 |
| -------------------------- | --------- | ------- | --------------------- |
| title                      | text      |         |                       |
| prompt                     | text      |         |                       |
| otherIcon                  | icon name |         |                       |
| otherLabel                 | text      |         |                       |
| requestTypeSubTypeSettings | array     |         | See config data below |

{% tabs %}
{% tab title="requestTypeSubTypeSettings Config Data" %}
| Config Data      | Options   | Notes |
| ---------------- | --------- | ----- |
| icon             | icon name |       |
| requestTypeId    | number    |       |
| requestTypeLabel | text      |       |
{% endtab %}

{% tab title="Example" %}
```
        "requestTypeSubTypeSettings": [
            {
                "icon": "power",
                "requestTypeId": 12,
                "requestTypeLabel": "Lighting"
            },
            {
                "icon": "thermometerHalf",
                "requestTypeId": 6,
                "requestTypeLabel": "Temperature"
            },
            {
                "icon": "tools",
                "requestTypeId": 1,
                "requestTypeLabel": "Building Svcs"
            },
            {
                "icon": "lock",
                "requestTypeId": 11,
                "requestTypeLabel": "Key/Locks"
            },
            {
                "icon": "broom",
                "requestTypeId": 1,
                "requestTypeLabel": "Cleaning Svcs"
            }
        ]
```
{% endtab %}
{% endtabs %}

watchedRequestsWidgetText

{% tabs %}
{% tab title="Config Data" %}
| Config Data | Options | Notes                                         |
| ----------- | ------- | --------------------------------------------- |
| widgetText  | array   | descText, typeText, requestText, locationText |
{% endtab %}

{% tab title="Example" %}
```
    "watchedRequestsWidgetText": {
        "widgetText": {
            "descText": "Description",
            "typeText": "Request Type",
            "requestText": "Work Request ",
            "locationText": "Location"
        }
    }
```
{% endtab %}
{% endtabs %}

## AppTree administrative configurations

#### submission\_error\_config

| Config Data          | Options | Example                                                                                                                                                      | Notes |
| -------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----- |
| title                | text    | A new work request for <\<RequestTypeDescription>> / <\<RequestSubTypeDescription>> in <\<PropertyDescription>> - <\<SpaceDescription>> could not be created |       |
| filter               | text    | submission\_errors                                                                                                                                           |       |
| subtitle             | text    | The following submission errors were identified: <\<ExceptionErrors>>                                                                                        |       |
| task\_url            | url     | https://assistants.apptreeio.com/task/at\_conversation\_begin                                                                                                |       |
| source\_name         | text    | FAMIS360 WO CREATE ERROR                                                                                                                                     |       |
| notified\_status     | text    | FAILED-NOTIFIED                                                                                                                                              |       |
| step\_description    | text    | Please review errors                                                                                                                                         |       |
| task\_retry\_count   | number  | 5                                                                                                                                                            |       |
| conversation\_name   | text    | ViewSubmissionError                                                                                                                                          |       |
| conversation\_status | text    | NEW                                                                                                                                                          |       |

{% hint style="warning" %}
How is this config used and what details can we add to the above items?
{% endhint %}

#### auth\_provider\_class

No config data label is used for this configuration.  This configuration will always be set to the value **`Facility360AuthProvider`**

#### assistant\_secret

No config data label is used for this configuration.  This configuration contains the secret key used for the project and this secret must match the secretKey for the firebase app record

#### famis\_task\_url

| Config Data | Options | Example                                      | Notes                                                        |
| ----------- | ------- | -------------------------------------------- | ------------------------------------------------------------ |
| task\_url   | url     | https://tasks.apptreeio.com/famis\_api\_task | When create WR submissions are performed this task is called |

#### task\_config

| Config Data       | Options    | Example                     | Notes                                                                                                     |
| ----------------- | ---------- | --------------------------- | --------------------------------------------------------------------------------------------------------- |
| ssoEnabled        | true/false | do not configure by default | App considers default to be false if this is not set.  Set to true is SSO is enabled for the project ID   |
| reprocessFailures | true/false | false                       | App considers default to be false if this is not set.  Set to true if submission failures will be retried |

{% hint style="warning" %}
Are there other configs to use with **reprocessFailures**?
{% endhint %}
