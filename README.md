<p align="center">
  <img width="900" height="500" alt="image" src="https://github.com/user-attachments/assets/2c068a6c-d82b-4a43-ad32-d9fe559e1837" />
</p>

# okta-enterpirse-sso






---

### 1) SAML App Creation

1. Open the **Applications** tab then go to **Applications**
2. Select **Create App Integration** then select **SAML 2.0** then **Next**
3. On the **General Settings** page enter the following infomration:
  - **App Name:** Slack SP - Kennon Technologies

<p align="center">
  <img width="1038" height="520" alt="image" src="https://github.com/user-attachments/assets/0d112c1e-19a5-4931-98cf-74f714b0d8a4" />
</p>

4. On the **Configure SAML** page enter the following information:
   - **Single Sign On URL (ACS URL):** http://localhost:5001/saml/acs
   - **Audience URI (Entity ID):** http://localhost:5001/saml/metadata
   - **Name ID Format:** EmailAddress
   - **Application Username:** Email
  
<p align="center">
  <img width="1033" height="642" alt="image" src="https://github.com/user-attachments/assets/ee0fa695-6dec-46f3-bd92-c01005c7eb5a" />
</p>

5. On the **Feedback** page check **This  Is An Internal App That We Have Created** then **Finish**

<p align="center">
  <img width="783" height="326" alt="image" src="https://github.com/user-attachments/assets/98fe27f5-4f5a-4ab8-a803-38fc6ba91750" />
</p>
