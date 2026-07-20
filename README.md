<p align="center">
  <img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/2c068a6c-d82b-4a43-ad32-d9fe559e1837" />
</p>

# Okta SAML 2.0 Application Integration

This project demonstrates the configuration of SAML 2.0 application integrations 
in Okta, simulating the Single Sign-On responsibilities of an IAM Analyst or 
Identity Engineer in an enterprise environment. Building on the Active Directory 
integration and RBAC model established in previous labs, this lab walks through 
the core SAML 2.0 concepts and terminology, creating custom SAML app integrations 
in Okta, configuring group-based application access to enforce the principle of 
least privilege, and deploying multiple Service Provider app integrations to 
simulate a real enterprise application portfolio. All configurations are hands-on 
in a live Okta Integrator org and reflect real-world IAM practices around 
federated identity, application access governance, and SSO policy design.

---

## Prerequisites

This is the fourth lab of the [Okta IAM Lab Series](https://github.com/RyanKennon/Okta-Lab-Series/tree/main).
Complete all previous labs before starting this one.

The following should be in place before starting:

- Active Okta Integrator org with users, groups, and policies configured from previous labs
- Active Directory integration configured and synced from Lab 2
- RBAC group structure in place from Lab 3 (Finance, IT, Human Resources, Helpdesk, Cloud Engineer)
- All users imported and active in Okta

---

## Environments and Technologies Used

- Okta Identity Cloud (Integrator Free Plan)
- Okta Admin Console
- Okta Application Integration Network (SAML 2.0)
- Okta Universal Directory

---

## Table of Contents

- [1) Custom SAML App Creation](#1-custom-saml-app-creation)
- [2) Group-Based App Access](#2-group-based-app-access)
- [3) Multiple SP Configuration](#3-multiple-sp-configuration)

---

### 1) Custom SAML App Creation

Creating a custom SAML 2.0 app integration in Okta establishes the trust 
relationship between Okta as the Identity Provider and the Service Provider 
application. Configuring the ACS URL, Audience URI, and NameID format defines 
how Okta will communicate with the SP during the authentication flow.

1. Open the **Applications** tab then go to **Applications**
2. Select **Create App Integration** then select **SAML 2.0** then **Next**
3. For the **App Name** enter **Slack SP - Kennon Technologies** then **Next**

<p align="center">
  <img width="787" height="439" alt="image" src="https://github.com/user-attachments/assets/5a7ed5ac-3c12-4dd1-865d-bfd189dcbb88" />
</p>

4.  On the **Configure SAML** page enter the following information then select **Next:**
   - **Single Sign On URL:** https://yourapp.example.com/saml/acs
   - **Audience URI (SP Entity ID):** https://yourapp.example.com/saml/metadata
   - **Name ID Format:** EmailAddress
   - **Application Username:** Email
  
<p align="center">
  <img width="1033" height="642" alt="image" src="https://github.com/user-attachments/assets/ee0fa695-6dec-46f3-bd92-c01005c7eb5a" />
</p>

5. On the **Feedback** page check **This  Is An Internal App That We Have Created** then **Finish**

<p align="center">
  <img width="783" height="326" alt="image" src="https://github.com/user-attachments/assets/98fe27f5-4f5a-4ab8-a803-38fc6ba91750" />
</p>

---

### 2) Group-Based App Access

Group-based app access ensures that application access in Okta is controlled 
exclusively through group membership rather than direct user assignment. 
Assigning role groups to the SAML app enforces the least privilege principle 
established in the RBAC lab and ensures access is automatically inherited 
based on a user's group membership.

1. Open the **Applications** tab then **Applications**
2. Open the **Slack SP - Kennon Technologies** page then open the **Assignments** tab
3. Click **Assign** then **Assign to Groups**
4. **Assign** the app to the **Finance** group then press **Done**

<p align="center">
  <img width="607" height="627" alt="image" src="https://github.com/user-attachments/assets/319f5a76-408c-4bae-b350-6f1c953a47f0" />
</p>

5. Do the same with the **IT, Human Resources, Helpdesk, and Cloud Engineer** groups as well

<p align="center">
  <img width="759" height="640" alt="image" src="https://github.com/user-attachments/assets/383d412c-2c82-4739-bc4f-93d587772a28" />
</p>

---

### 3) Multiple SP Configuration

Configuring multiple SAML Service Provider applications demonstrates that each 
application maintains its own unique trust relationship with Okta, with separate 
ACS URLs and Audience URIs. Assigning different groups to each app reflects a 
real enterprise access matrix where different roles have access to different 
applications.

1. Open the **Applications** tab then **Applications**
2. Select **Create App Integration** then **SAML 2.0** then **Next**
3. Name the app: **Google Workspace SP - Kennon Technologies** then click **Next**
4. On the **Configure SAML** page enter the following information then click **Next**:
   - **Single Sign-On URL:** https://yourapp.example.com/gworkspace/saml/acs
   - **Audience URI:** https://yourapp.example.com/gworkspace/saml/metadata
   - **Name ID Format:** EmailAddress
   - **Application Username:** Email
5. On the **Feedback** tab check **This is an Internal App that We Have Created** then **Finish**
6. Open the **Assignments** tab then click the **Assign** dropdown then **Assign to Groups**
7. **Assign** the **Human Resources** and **Cloud Engineer** groups to the app then **Done**

<p align="center">
  <img width="779" height="456" alt="image" src="https://github.com/user-attachments/assets/24b59644-f66e-4796-951c-49ff41b80028" />
</p>

8. Go **Back to Applications** then **Create App Integration** select **SAML 2.0** then **Next**
9. Name the app: **Sharepoint SP - Kennon Technologies** then click **Next**
10. On the **Configure SAML** page enter the following information then click **Next**:
   - **Single Sign-On URL:** https://yourapp.example.com/sharepoint/saml/acs
   - **Audience URI:** https://yourapp.example.com/sharepoint/saml/metadata
   - **Name ID Format:** EmailAddress
   - **Application Username:** Email
11. On the **Feedback** tab check **This is an Internal App that We Have Created** then **Finish**
12. Open the **Assignments** tab then click the **Assign** dropdown then **Assign to Groups**
13. **Assign** the **Finance, IT, Human Resources, and Cloud Engineer** groups to the app then **Done**

<p align="center">
  <img width="758" height="581" alt="image" src="https://github.com/user-attachments/assets/447a90b8-4f8f-4ffe-ab1a-0a717117b9c8" />
</p>

14. In an **Incognito** browser sign in to **Okta** as **John Smith**
15. Confirm that the **Slack SP** and the **Sharepoint SP** apps appear

<p align="center">
  <img width="587" height="352" alt="image" src="https://github.com/user-attachments/assets/8873e218-4762-4ea6-8679-0425622b0054" />
</p>

16. In an **Incognito** browser sign in to **Okta** as **John Smith**
17. Confirm that the **Slack SP** and the **Sharepoint SP** apps appear

<p align="center">
  <img width="587" height="352" alt="image" src="https://github.com/user-attachments/assets/88933ffe-6e15-4867-bcf7-846cc00b212f" />
</p>

18. In an **Incognito** browser sign in to **Okta** as **Lisa Park**
19. Confirm that the **Slack SP, Sharepoint SP, and the Google Workspace SP** apps appear

<p align="center">
  <img width="560" height="347" alt="image" src="https://github.com/user-attachments/assets/0c4457b5-932b-450d-91dc-461d7804aca2" />
</p>

---

> **Note:** This lab is intentionally left open. The SAML app integrations 
> configured here serve as the foundation for subsequent Okta labs. Continue 
> to the [Okta IAM Lab Series](https://github.com/RyanKennon/Okta-Lab-Series/tree/main) 
> for the next lab in the series.

---

<p align="left">
  <a href="https://github.com/RyanKennon/Okta-RBAC">⬅ Lab 3 — Okta RBAC Design & Implementation</a>
</p>

<p align="right">
  <a href="https://github.com/RyanKennon/okta-mfa-adaptive-authentication">Lab 5 — Okta MFA & Adaptive Authentication ➡</a>
</p>
