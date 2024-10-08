<!--startmeta
custom_edit_url: "https://github.com/netdata/netdata/edit/master/integrations/cloud-authentication/integrations/scim.md"
meta_yaml: "https://github.com/netdata/netdata/edit/master/integrations/cloud-authentication/metadata.yaml"
sidebar_label: "SCIM"
learn_status: "Published"
learn_rel_path: "Netdata Cloud/Authentication & Authorization/Cloud Authentication & Authorization Integrations"
message: "DO NOT EDIT THIS FILE DIRECTLY, IT IS GENERATED BY THE AUTHENTICATION'S metadata.yaml FILE"
endmeta-->

# SCIM


<img src="https://netdata.cloud/img/scim.svg" width="150"/>


The System for Cross-domain Identity Management (SCIM) specification is designed to simplify the management of user identities in cloud-based applications and services.


<img src="https://img.shields.io/badge/maintained%20by-Netdata-%2300ab44" />

## Setup

### Prerequisites
- A Netdata Cloud account
- Admin access to the Space
- The Space must be on a paid plan
- OIDC/SSO integration must already be enabled in one of your Spaces

### Netdata Configuration Steps
1. Click on the Space settings cog (located above your profile icon).
2. Click on the **User Management** section and access **Authentication and Authorization** tab.
3. In the SCIM card, click on **Activate**.
4. Depending on your situation:
   - If OIDC/SSO integration is already enabled in your Space, click **Activate**.
   - If you already have a SCIM integration in another Space and want to create a linked integration here, enter the SCIM token from the original integration and click **Activate**.
5. If the setup is successful, you will receive two parameters:
   - **Base URL**: Use this URL as the base URL for your SCIM client.
   - **Token**: Use this token for Bearer Authentication with your SCIM client.

### Rotating the SCIM Token
You can rotate the token provided during SCIM integration setup if needed.

Steps to rotate the token:
1. Click on the Space settings cog (located above your profile icon).
2. Click on the **User Management** section and access **Authentication and Authorization** tab.
3. In the already configured SCIM card, click **Configure**.
4. Click **Regenerate Token**.
5. If successful, you will receive a new token for Bearer Authentication with your SCIM client.

### Supported Features
This integration adheres to SCIM v2 specifications. Supported features include:

- User Resource Management (urn:ietf:params:scim:schemas:core:2.0:User)
- Patch operations: Supported
- Bulk operations: Not supported
- Filtering: Supported (max results: 200)
- Password synchronization: Not supported, as we rely on SSO/OIDC authentication
- eTag: Not supported
- Authentication schemes: OAuth Bearer Token

### User Keying Between SCIM and OIDC
Our SCIM (System for Cross-domain Identity Management) integration utilizes OIDC (OpenID Connect) to authenticate users.
To ensure users are correctly identified and authenticated between SCIM and OIDC, we use the following mapping:

- SCIM externalID ↔ OIDC sub

This mapping ensures that the identity of users remains consistent and secure across both systems.

**Important**: Ensure that your OIDC and SCIM systems follow this mapping strictly.
The externalID in SCIM must correspond to the subfield in OIDC. Any deviation from this mapping may result
in incorrect user identification and authentication failures.

### Reference
[SCIM Specification](https://scim.org)


