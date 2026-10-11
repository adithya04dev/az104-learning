# OAuth2 Proxy Assessment

## Objective

Assess whether OAuth2 Proxy implementation is required for the following applications:

- CDP Metrics
- CDP Runtime
- OpenSearch
- DSO ELK

The assessment focuses on existing authentication mechanisms, native Microsoft Entra ID integration capabilities, and whether OAuth2 Proxy provides any additional value.

## 1. Existing Architecture – Runtime Platform

*[Insert existing ELK authentication architecture diagram]*

The Runtime Platform currently uses OAuth2 Proxy as a shared authentication layer for multiple applications, such as Grafana and ELK.

**Purpose:**
- Centralize authentication across multiple applications.
- Integrate with the organization's identity provider.
- Avoid implementing separate authentication mechanisms for applications that do not support OIDC natively.

## 2. Application-Level Assessment

| Application | Authentication Approach | OAuth2 Proxy Assessment |
|---|---|---|
| CDP Runtime | Shared OAuth2 Proxy | Existing shared implementation; retain unless architecture changes |
| CDP Metrics | Entrycar / organizational SSO | Likely not required; validate existing authentication flow |
| OpenSearch | Microsoft Entra ID via OIDC; Basic Auth for applicable clients | Likely not required for interactive access with native OIDC |
| DSO ELK | Entrycar / organizational SSO | Needs validation of native authentication support |

## 3. Key Findings

OAuth2 Proxy is primarily useful when multiple applications require a common authentication layer or when applications lack native OIDC support.

For dedicated deployments such as CDP Metrics and OpenSearch, a separate OAuth2 Proxy implementation may not be necessary if the existing authentication mechanism already meets the organization's security requirements.

Applications supporting native OIDC can integrate directly with Microsoft Entra ID without introducing an additional authentication proxy.

However, **having a dedicated cluster alone does not eliminate the need for OAuth2 Proxy**. The decision depends on the application's authentication capabilities and security requirements.

OAuth2 Proxy may not be necessary when:

- The application already supports OIDC authentication natively.
- An existing authentication gateway or proxy handles the required authentication and authorization.
- The existing SSO implementation satisfies organizational security requirements.

## 4. Documentation Review

Reviewed available CSO SharePoint documentation and support-channel discussions for any mandate requiring OAuth2 Proxy implementation.

**Finding:** No explicit OAuth2 Proxy implementation requirement was identified for CDP Runtime, CDP Metrics, OpenSearch, or DSO ELK in the reviewed sources.

This does not confirm that the requirement is absent from all organizational security standards.

## 5. Preliminary Conclusion

Based on the current assessment, OAuth2 Proxy does not appear to be universally required across these applications.

For applications with native Entra ID/OIDC integration or an existing compliant authentication solution, introducing OAuth2 Proxy may add unnecessary operational complexity.

**Final confirmation is pending** regarding any CSO or platform-specific requirement to implement OAuth2 Proxy.

## 6. Action Items

- Confirm with Sreedhar whether OAuth2 Proxy is mandatory for these applications.
- Validate whether the existing Entrycar authentication implementation meets the required security standards.
- Confirm native OIDC support and authorization requirements for each application.
- Finalize the application-specific recommendation based on the confirmation.



Hi Sreedhar, we're looking into whether OAuth2 Proxy is required for our ELK applications.

Just wanted to check if OAuth2 Proxy is mandatory or if Entra ID integration through Entrycar would be sufficient.

I noticed the Runtime Platform uses a shared OAuth2 Proxy, whereas we have halo.e/AAF authorization through Entrycar containers.