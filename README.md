<p align="center">
  <img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/2c068a6c-d82b-4a43-ad32-d9fe559e1837" />
</p>

# okta-enterpirse-sso






---

### 1) Custom SAML App Creation

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

6. On the **Feedback** page check **This  Is An Internal App That We Have Created** then **Finish**

<p align="center">
  <img width="783" height="326" alt="image" src="https://github.com/user-attachments/assets/98fe27f5-4f5a-4ab8-a803-38fc6ba91750" />
</p>

---

### 2) Group-Based App Access

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
