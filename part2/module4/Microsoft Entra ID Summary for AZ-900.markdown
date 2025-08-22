# Microsoft Entra ID Summary for AZ-900

Microsoft Entra ID (formerly Azure Active Directory) is a cloud-based identity and access management (IAM) service that provides secure access to Azure, Microsoft 365, and other cloud applications. It is a core component of Microsoft Azure and is essential for the AZ-900: Microsoft Azure Fundamentals exam. Below is an objective summary of key concepts related to Microsoft Entra ID for the exam.

## Key Characteristics
- **Cloud-Based Service**: Unlike on-premises Active Directory Domain Services (ADDS), Entra ID is designed for cloud environments and does not require managing physical servers.
- **Identity and Access Management**: Manages user identities, authentication, and authorization for accessing resources.
- **Integration**: Supports Azure, Microsoft 365, Dynamics 365, and third-party SaaS applications using protocols like SAML, OAuth, and OpenID Connect.
- **Editions**: Available in Free, Premium P1, and Premium P2 editions, with varying features (e.g., Free edition lacks SLA, while Premium includes advanced features like Conditional Access).

## Core Features
- **Single Sign-On (SSO)**: Allows users to access multiple applications with one set of credentials, improving user experience and reducing administrative overhead.
- **Multi-Factor Authentication (MFA)**: Enhances security by requiring additional verification (e.g., password + mobile code) to prevent unauthorized access.
- **Conditional Access**: Enables policies to control access based on conditions like user location, device type, or risk level.
- **Role-Based Access Control (RBAC)**: Assigns permissions based on roles to manage access to Azure resources securely.
- **Identity Protection**: Detects and mitigates identity-based risks, such as suspicious sign-ins or compromised credentials, with automated responses like password resets.
- **B2B and B2C Collaboration**: Supports secure access for external partners (B2B) and customers (B2C) through guest user invitations.
- **Device Management**: Enforces policies to ensure only compliant devices access resources.
- **Application Management**: Centralizes authentication for custom and third-party applications.

## Key Use Cases
- **Secure User Access**: Ensures only authorized users access resources through MFA and Conditional Access.
- **Partner Collaboration**: Simplifies secure access for external partners via B2B invitations.
- **Application Access Control**: Provides centralized authentication for applications, eliminating the need for custom identity solutions.
- **Hybrid Identity**: Integrates with on-premises Active Directory using Microsoft Entra Connect for synchronized user management.

## Differences from Active Directory
- **Purpose**: Entra ID is for cloud-based authentication, while ADDS is for on-premises environments.
- **Network**: Entra ID operates over the internet, ADDS over an intranet.
- **Protocols**: Entra ID uses SAML, OAuth, and OpenID; ADDS uses LDAP and Kerberos.
- **Microsoft Entra Domain Services**: A PaaS version of ADDS for cloud-based domain controller capabilities without managing VMs.

## Key Exam Points
- **Tenants and Directories**: A tenant is an instance of Entra ID, containing a directory for users, devices, and applications. Created automatically upon Azure sign-up.
- **User and Group Management**: Users can be created internally or invited as guests. Groups (Security or Microsoft 365) streamline access and license management.
- **Zero Trust**: Entra ID aligns with the Zero Trust security model, assuming no inherent trust and verifying every access request.
- **Integration with Azure**: Manages authentication for Azure portal access and resource management via RBAC.

## Benefits
- **Security**: Provides robust authentication and risk detection to protect against cyber threats.
- **Efficiency**: Centralizes identity management, reducing administrative complexity.
- **Scalability**: Scales without additional hardware, supporting growing organizational needs.
- **Compliance**: Helps meet industry security standards through features like MFA and Conditional Access.

## Study Resources
- Microsoft Learn: Offers free self-paced learning paths for AZ-900, including modules on Entra ID.
- Practice Assessments: Available on Microsoft Learn to test knowledge with exam-style questions.
- Documentation: Refer to Microsoft Entra ID official documentation for detailed insights.

This summary covers the essential aspects of Microsoft Entra ID for the AZ-900 exam, focusing on its role, features, and benefits in Azure’s ecosystem.[](https://learn.microsoft.com/en-us/credentials/certifications/resources/study-guides/az-900)[](https://idodata.com/2025/06/26/az-900-define-and-describe-the-functionality-and-usage-of-microsoft-entra-id/)[](https://notes.kodekloud.com/docs/AZ900-Microsoft-Azure-Fundamentals/Identity-Access-and-Security/Microsoft-Entra-ID)