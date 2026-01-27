# Overview
As a penetration tester, I assessed the security of the application’s analytics functionality and identified a blind SQL injection vulnerability in the TrackingId cookie. The issue arose from unsafe inclusion of user-controlled cookie data in a backend SQL query executed asynchronously. By crafting an out-of-band payload and leveraging Burp Collaborator, I was able to exfiltrate sensitive database information via DNS interactions, extract the administrator’s credentials, and gain unauthorized administrative access. This project highlights how blind SQL injection flaws can be reliably exploited using OAST techniques when in-band responses are unavailable.

# Steps Undertaken

Step 1: Identified the TrackingId cookie as a potential injection point during request analysis.

Step 2: Injected a crafted SQL payload designed to trigger out-of-band DNS interactions.

Step 3: Monitored Burp Collaborator for external interactions initiated by the database query.

Step 4: Extracted administrator credentials from the DNS response and authenticated as the admin user.

# Conclusion

This assessment confirmed a critical blind SQL injection vulnerability that enabled out-of-band data exfiltration and full administrative compromise. The findings reinforce the importance of parameterized queries and strict handling of all user-controlled input, including cookies.
