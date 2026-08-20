# federated-user
Cloud identity federation lab implementing SAML 2.0 SSO between Microsoft Entra ID and AWS IAM Identity Center for centralized, credential-less access control
### 1. Entra ID Enterprise Application Setup
Configured the **AWS IAM Identity Center** Enterprise Application within Microsoft Entra ID to establish the SAML 2.0 service provider trust.
![Entra ID App Setup](./1-entra-enterprise-app-setup.png)

---

### 2. SAML Attribute & Claims Mapping
Mapped the `Unique User Identifier (Name ID)` claim to `user.mail` to bypass external guest account UPN character restrictions (`#EXT#`).
![Entra ID Claims Mapping](./2-entra-saml-claims-mapping.png)

---

### 3. AWS Identity Source Configuration
Switched the IAM Identity Center Identity Source to **External identity provider** and imported the Entra ID SAML metadata.

![AWS Identity Source](./3-aws-identity-source-config.png)

---

### 4. Account Assignment & Access Portal
Assigned the federated user identity to the target AWS account with the `Administratoraccess` permission set.

![AWS Account Assignment](./4-aws-portal-account-assignment.png)
