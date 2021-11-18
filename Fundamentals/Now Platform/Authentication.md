# Authentication
**Local Database:** Authenticates the username and password stored in their corresponding user record in the ServiceNow instance.

**External Single Sign-On:** Authenticates the username and password configured in identity providers that have a matching user account in the ServiceNow instance.

**LDAP:** Authenticates the username and password in their LDAP (Lightweight Directory Access Protocol) account that has a matching user account in the ServiceNow instance.

**OAuth 2.0:** Authenticates the username and password of OAuth identity provider that has a matching user account in the ServiceNow instance.

**Digest Token:** Authenticates on encrypted digest of the username and password stored in the user record.

**Multi-Factor:** Authenticates the username and password in the ServiceNow instance and sends a pass code to the user's mobile device where an authenticator supporting Time-based On-Time Password (TOTP) is installed such as Google Authenticator.