# dashboard\_config

The dashboard\_config settings will control which widgets will display on the dashboard for the user within the assistant.  These include the following:

* Banner image
* Contact/Help information
* Create request button options
* My open requests
* My recently closed requests
* All requests
* My watched requests
* "Due" requests ?????
* Search my requests
* Search all requests

## Widget configuration options

When configuring each of the above-mentioned widgets for a customer's dashboard, you will need to include the following for each.

### General configurations

| Config Data    | Options | Example | Notes |
| -------------- | ------- | ------- | ----- |
| appDescription | text    |         |       |

namedGreetingOptions

| Config Data | Options    | Example | Notes |
| ----------- | ---------- | ------- | ----- |
| useFirst    | true/false |         |       |
| useLast     | true/false |         |       |
| useFull     | true/false |         |       |
| useUsername | true/false |         |       |

{% hint style="info" %}
Configuration mainMenu (array) was used in early versions of the FAMIS360 assistant.  This is no longer used and does not need to be configured for customers.

```
  mainMenu: {
    title: string;
    description: string;
    refreshInterval?: number;
  };
```
{% endhint %}

### Banner image

| Config Data      | Options | Example | Notes                                                                                               |
| ---------------- | ------- | ------- | --------------------------------------------------------------------------------------------------- |
| bannerImageUrl   | url     |         |                                                                                                     |
| bannerImageScale | number  |         | Only need to set this if the banner image should be the full width because not using contact widget |

### Contact/Help Information

| Config Data           | Options | Example | Notes |
| --------------------- | ------- | ------- | ----- |
| helpText              | text    |         |       |
| contactMarkdownString | text    |         |       |

contactWidgetText

| Config Data | Options | Example | Notes |
| ----------- | ------- | ------- | ----- |
| title       |         |         |       |
| details     |         |         |       |
| phone       |         |         |       |
| email       |         |         |       |

### Create request button options

| Config Data     | Options    | Example | Notes |
| --------------- | ---------- | ------- | ----- |
| stepFlowEnabled | true/false |         |       |

requestTypeSubTypeWidget

| Config Data                | Options   | Example | Notes                                |
| -------------------------- | --------- | ------- | ------------------------------------ |
| title                      | text      |         |                                      |
| description                | text      |         | Displays below the button title text |
| prompt                     | text      |         |                                      |
| otherIcon                  | icon name |         |                                      |
| otherLabel                 | text      |         |                                      |
| refreshInterval            | number    |         |                                      |
| requestTypeSubTypeSettings | array     |         | See config data below                |

{% tabs %}
{% tab title="requestTypeSubTypeSettings Config Data" %}
| Config Data         | Options    | Notes                                                                                                          |
| ------------------- | ---------- | -------------------------------------------------------------------------------------------------------------- |
| icon                | icon name  |                                                                                                                |
| requestTypeId       | number     |                                                                                                                |
| requestSubTypeId    | number     |                                                                                                                |
| requestTypeLabel    | text       | This is the value that displays on the button                                                                  |
| requestSubTypeLabel | text       | This is displayed in the CW setup assistant                                                                    |
| restrictEdit        | true/false | If true, then when on create request form the user is restricted from editing the type/subtype values selected |
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

requestTypeWidget is a legacy configuration that should no longer be used for new implementations.  Use requestTypeSubTypeWidget configuration instead

### My open requests

| Config Data         | Options    | Example | Notes |
| ------------------- | ---------- | ------- | ----- |
| openRequestsEnabled | true/false |         |       |
| openRefreshInterval | number     | 30      |       |

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

### My recently closed requests

| Config Data              | Options    | Example | Notes |
| ------------------------ | ---------- | ------- | ----- |
| closedRequestsEnabled    | true/false |         |       |
| closedRequestSize        | number     | 500     |       |
| closedRefreshInterval    | number     | 30      |       |
| closedRequestsWithinDays | number     | 60      |       |

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

### All requests

| Config Data             | Options    | Example | Notes |
| ----------------------- | ---------- | ------- | ----- |
| allRequestsEnabled      | true/false |         |       |
| allRequestsNumberToShow | number     | 25      |       |
| allRefreshInterval      | number     | 6000    |       |
| allHistoryDays          | number     | 90      |       |

allRequestsWidgetText

{% tabs %}
{% tab title="Config Data" %}
| Config Data | Options | Notes                                         |
| ----------- | ------- | --------------------------------------------- |
| widgetText  | array   | descText, typeText, requestText, locationText |
{% endtab %}

{% tab title="Example" %}
```
    "allRequestsWidgetText": {
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

### My watched requests

| Config Data            | Options    | Example | Notes |
| ---------------------- | ---------- | ------- | ----- |
| watcherRequestsEnabled | true/false |         |       |
| watcherRefreshInterval | number     | 6000    |       |

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

### Due requests

| Config Data           | Options    | Example | Notes |
| --------------------- | ---------- | ------- | ----- |
| dueRequestsEnabled    | true/false |         |       |
| dueRequestsFutureDays | number     | 30      |       |
| dueRefreshInterval    | number     | 6000    |       |

dueRequestsWidgetText

{% tabs %}
{% tab title="Config Data" %}
| Config Data | Options | Notes                                         |
| ----------- | ------- | --------------------------------------------- |
| widgetText  | array   | descText, typeText, requestText, locationText |
{% endtab %}

{% tab title="Example" %}
```
    "dueRequestsWidgetText": {
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

### Search my requests

searchRequests

| Config Data     | Options | Example | Notes |
| --------------- | ------- | ------- | ----- |
| title           | text    |         |       |
| prompt          | text    |         |       |
| description     | text    |         |       |
| refreshInterval | number  |         |       |

### Search all requests

| Config Data          | Options | Example | Notes |
| -------------------- | ------- | ------- | ----- |
| allSearchHistoryDays | number  | 30      |       |

searchAllRequests

| ConfigData      | Options | Example | Notes |
| --------------- | ------- | ------- | ----- |
| title           | text    |         |       |
| prompt          | text    |         |       |
| description     | text    |         |       |
| refreshInterval | number  |         |       |
