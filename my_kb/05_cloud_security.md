# Cybersecurity Study Notes: Cloud Security

# Cloud Security
Cloud security operates under a shared responsibility model: the cloud provider secures the underlying infrastructure, while the customer remains responsible for securing their own data, identities, and configurations. Misconfigured storage buckets and overly permissive identity policies are among the leading causes of cloud data breaches. Cloud security posture management (CSPM) tools continuously audit configurations against best practices and flag risky settings before attackers can exploit them.

## Additional study notes (AI-assisted draft; review before submission)
Shared responsibility varies with the cloud service model, but customers normally remain responsible for how they use identities, configure access, and protect the data they place in a service. A security review should ask who can access a storage resource, whether access is publicly exposed, and how configuration changes are recorded. Cloud security posture management assists with finding configurations that diverge from policy, but a finding must still be assessed in context.

A useful cloud incident scenario is an overly broad service-account role: even if the cloud provider protects the underlying infrastructure, the customer may inadvertently grant an application more access than needed. Least-privilege access, explicit configuration reviews, and timely remediation lower this risk. The purpose of documenting responsibility is to clarify which team can prevent, detect, and respond to a specific configuration failure rather than assume that all cloud security is automatically handled by the provider.
