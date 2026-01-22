# Lab 1: Identity & Access Management (Azure Entra ID)

## Objective
The objective of this lab was to understand how identity and access are controlled in a cloud environment using Azure Entra ID, and to evaluate the security risks associated with excessive privileges and the enforcement of multi-factor authentication (MFA).

---

## Environment
**Platform:** Microsoft Azure  
**Identity Service:** Azure Entra ID  

### Accounts Created
- **Lab User** – Attribute Assignment Reader role  
- **Lab Admin** – Global Administrator role  

### Security Controls Tested
- Role-Based Access Control (RBAC)  
- Multi-Factor Authentication (MFA)

---

## Lab Setup
Two user accounts were created within Azure Entra ID to represent different access levels:
- A standard user with limited, read-only permissions  
- A privileged user with full administrative permissions  

Roles were assigned using Azure RBAC to enforce the principle of least privilege.

---

## Testing & Observations

### 1. Role-Based Access Control (RBAC)
- The **Lab User** with the Reader role could view users and directory information but was restricted from making any changes.  
- The **Lab Admin** with the Global Administrator role had unrestricted access, including the ability to modify users, roles, and authentication settings.

**Observation:**  
RBAC effectively limited the actions of low-privileged users while granting full control to privileged accounts.

---

### 2. Multi-Factor Authentication (MFA) Enforcement
- MFA was enabled on the **Lab Admin** account, requiring a second authentication factor during login.  
- An attempt was made to disable MFA on the Global Administrator account to simulate a security misconfiguration. However, Azure Entra ID enforces MFA on all Global Administrators by default and prevents it from being removed.

This behavior highlights Microsoft’s built-in protections for high-risk accounts and reinforces the importance of MFA for privileged identities. To demonstrate the risks associated with disabled MFA, a secondary high-privilege test account could be used with MFA disabled to simulate potential compromise scenarios.

**Observation:**  
Disabling MFA on privileged accounts significantly increases the risk of account compromise through credential-based attacks such as phishing or password reuse.

---

## Security Risks Identified
- Global Administrator accounts represent high-value targets due to their broad permissions.  
- Absence of MFA on privileged accounts allows attackers to gain full access if credentials are compromised.  
- Identity-based misconfigurations can undermine otherwise secure cloud environments.

---

## Mitigation & Best Practices
- Enforce MFA on all privileged accounts.  
- Apply the principle of least privilege by limiting administrative access.  
- Regularly audit role assignments and authentication methods.  
- Use conditional access policies to restrict high-risk sign-ins.

---

## Key Takeaways
- Identity is a primary attack vector in cloud environments.  
- Role-based access control reduces the blast radius of compromised accounts.  
- MFA is one of the most effective controls for preventing unauthorized access.  
- Azure enforces MFA by default on Global Administrators, demonstrating proactive cloud security practices.  
- Understanding enforced security controls is critical for assessing real-world cloud risk.

---

## Skills Demonstrated
- Cloud identity and access management  
- Role-based access control (RBAC)  
- Privileged access risk analysis
