# Self Registration

The FAMIS360 Assistant can be configured to have self-registration enabled.  This means that if a user account does not exist in FAMIS already, then when self-registration is enabled it will create the user account.  Self-registration can be enabled for assistants using SSO or native FAMIS360 user authentication.

## Self Registration:  Using native FAMIS360 authentication

When self-registration is enabled for an assistant using native FAMIS360 authentication, users have the ability to sign up for a user account.  Upon verification of the new account, then their user record will be created in FAMIS360 with the defaults configured for the environment.

On the sign-up form, the user enters their email address, password, name, and other required information.  Upon submission of the sign-up form, a verification email will be sent to them.  Clicking on the link in the email will trigger the verification process to complete and the user record will then be created in FAMIS360.

## Self Registration: Using SSO authentication

Assistants with self-registration enabled and SSO authentication configured will have their SSO configuration updated to be prefixed with 'FAMIS-'.  This triggers the AppTree self-registration task (`famis_sso_self_registration_task`) to be executed based on the SAML response received from the SSO authentication.

The self-registration task does the following:

* Searches for the user in FAMIS360 using the prefUsername attribute matching the FAMIS360 username
* Searches for the user in FAMIS360 using the email attribute matching the FAMIS360 username
* If a match is not found then the user is auto-provisioned in FAMIS360 using the user information from the SAML response and the defaults configured for the assistant's self-registration settings
* If a match is found, but the user is not active, then the FAMIS360 user record is updated to an Active status
