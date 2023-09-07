# AppTree administrative configurations

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
