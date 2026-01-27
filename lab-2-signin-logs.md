# Lab 3: Azure Sign-In Logs & Failed Login Analysis

## Goal
Analyze Azure AD sign-in logs to understand authentication failures and demonstrate how failed logins can indicate potential security threats.

## Tools Used
- Azure Active Directory
- Azure Sign-In Logs
- Azure Portal

## Steps Taken
1. Created a test Azure AD user (`signinlabuser`).
2. Generated multiple failed login attempts using incorrect credentials in a private browser session.
3. Reviewed Azure AD sign-in logs as an administrator:
   - Filtered by user (`signinlabuser`)
   - Filtered by status (Failure)
4. Analyzed individual log entries:
   - Failure reason
   - IP address
   - Timestamp
   - Authentication method
<img width="940" height="379" alt="Directory Logs" src="https://github.com/user-attachments/assets/c0f8e3d0-f9bf-4fd4-938c-04219c1e0bf0" />

5. Compared failed logins to a successful login for the same user.

## Results
- All failed login attempts were captured with detailed metadata.
- Failed login logs showed reasons, timestamps, and originating IPs.
- Successful login provided a contrast to highlight authentication behavior.
- Demonstrates how repeated failures could indicate brute-force attempts or compromised credentials.

## Lessons Learned
- Sign-in logs are critical for identity-based threat detection.
- Monitoring failed login attempts is a key part of cloud security operations.
- Understanding log metadata helps identify patterns and potential security incidents.

## Screenshots
- `screenshots/failed_logins.png` — filtered failed login attempts
- `screenshots/successful_login.png` — successful login for comparison
<img width="913" height="269" alt="Failed vs Success" src="https://github.com/user-attachments/assets/43ceeba0-a03b-4706-ac48-be35ff8040d4" />
