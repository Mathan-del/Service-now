# Phase 3: Automation using Flow Designer & Email Notification

When a student creates a new IT support ticket, they only enter the **Caller Name** and **Short Description**. They do not select Category or Subcategory. After submission, a Flow Designer automation is triggered and checks the Short Description for keywords such as WiFi, Projector, Password, or Slow, then assigns the Category and Subcategory automatically.

| If short description contains | Category | Subcategory |
|---|---|---|
| WiFi | Network | WiFi |
| Projector | Hardware | Projector |
| Password / Login | Access | Forgot Password |
| Slow / Hanging | Performance | Slow Computer |

This ensures consistent classification, removes human error, and reduces manual effort. The whole process is no-code, easy to maintain and scalable.

## Activity 1: Auto Classification using Flow Designer
1. Go to All menus → search **Flow Designer**.
2. Under Process Automation open **Flow Designer**.
3. Top right: click **New** → select **Flow**.
4. Name: **Auto Classify School IT Tickets**.
5. Application: **Global**.
6. Click **Build Flow**.

## Activity 2: Trigger Configuration
- Trigger: **Record Created**
- Table: **Incident Workflow**
- Condition: **Category is Empty**
- Click **Done**.

Then, under Actions, select **Flow Logic**.

## Activity 3: Wi-Fi Issue Classification
1. Select **If** condition.
2. Condition label: *SD is Wifi or Network* (any name you like).
3. Condition 1: Short description **Contains** `Wi-Fi`.
4. Condition 2: Short description **Contains** `Network`.
5. Click **Done**.
6. Add Action → **Update Record**.
   - Table: auto-fills as Incident Workflow.
   - Set Category = **Network**
   - Set Subcategory = **Wi-Fi**
7. Click **Done**.

## Activity 4: Projector Issue Classification
1. Select **Else If**.
2. Label: *SD is Projector or Hardware*.
3. Condition: Short description **Contains** `Projector`.
4. Click **Done**.
5. Action → **Update Record**: Category = **Hardware**, Subcategory = **Projector**.
6. Click **Done**.

## Activity 5: Password Issue Classification
1. Select **Else If**.
2. Label: *SD is Forgot password*.
3. Condition: Short description **Contains** `Forgot password`.
4. Click **Done**.
5. Action → **Update Record**: Category = **Access**, Subcategory = **Forgot Password**.
6. Click **Done**.

## Activity 6: Slow Computer Classification
1. Select **Else If**.
2. Label: *SD is Performance*.
3. Condition: Short description **Contains** `Slow Computer`.
4. Click **Done**.
5. Action → **Update Record**: Category = **Performance**, Subcategory = **Slow Computer**.
6. Click **Done**.

## Activity 7: Email Action Setup
After classification, add the **Send Email** action:
- To: **Caller → Email**
- Subject: *Your Request for the issue has been submitted.*
- Body: Ticket confirmation message.
- Click **Done**.

Finally, click **Activate** (top right corner).
