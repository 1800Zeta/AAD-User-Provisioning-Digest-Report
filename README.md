## USER PROVISIONING DIGEST REPORT

Author: asmalser

 - Reads all user account provisioning events from the Azure AD graph for a specificed time period, and emits a digest report.  

- The digest report is written to a text file on the host system, and can also be sent over email using an Office365 email account

- This script can be scheduled to run at any desired time interval using the Windows Task Scheduler

- Requires an application entry and secret key to be registered in the Azure AD tenant where the provisioning events exist, as described at:
 https://docs.microsoft.com/en-us/azure/active-directory/active-directory-reporting-api-prerequisites-azure-portal
 
 ## Update July 2019
- Updated to use graph.microsoft.com
- Requires additional permission - AuditLog.Read.All

## Params
ClientID        - Client ID of the application registered in AAD
ClientSecret    - Secret of application registered in AAD
tenantdomain    - AAD Tenant; for example, contoso.onmicrosoft.com
sendEmail       - Boolean to send an email or not
UseInternalSMTP - Boolean if you're using Office 365 set false, else set true
GenerateFile    - Boolean, useful to test, outputs a file rather than sending email
emailRecipients - Comma separated list of recipient email addresses
emailFrom       - Email address sending from
emailUsername   - Username if your email server requires Authentication
emailPassword   - Password if email server requires auth (need to convert to secure string)
SMTPServer      - address of SMTP server to use if different to O365
