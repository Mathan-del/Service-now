# Phase 2: Backend Development & Configuration

## Activity 1: Creation of Custom Table to Store Ticket Records

Steps to create the custom table:
1. Open All menus → search for **Tables**.
2. Under System Definition → click **Tables**.
3. On the top right corner click **New**.
4. Label: **Incident WorkFlow**.
5. Uncheck **Create module**.
6. Save the form.
7. Go to the **Controls** section and enable the **Auto Number** checkbox.
8. Save the form again.
9. Under Related Links click **Show Form**.
10. Open the Context Menu → Configure → **Form Designer**.
11. Create the required fields.

## Activity 2: Field Creation and Data Type Configuration

Objective: create all required fields in the School IT Ticket table with correct data types, choices, and dependencies, ensuring structured and consistent data capture.

| Field Label | Type | Reference / Choice |
|---|---|---|
| Number | Auto Number | — |
| Caller | Reference | sys_user |
| Category | Choice | Network, Hardware, Access, Performance |
| Subcategory | Choice | Wi-Fi, Projector, Forgot Password, Slow Computer |
| Short Description | String | — |
| Description | String | — |
| State | Choice | New, In progress, On hold, Resolved, Closed |
| Assigned Group | Reference | sys_user_group |
| Assigned to | Reference | sys_user |

After creating the fields with their types, add the choices from the Form Designer to all the choice-list fields: **Category, Subcategory and State**.

Then click **Save** (top right), open the form and reload it.

## Activity 3: Dependency Between Category and Subcategory

Objective: make the Subcategory options change dynamically based on the selected Category.

Navigation Steps:
1. Open the created table form and right-click the **Subcategory** field.
2. Click **Configure Dictionary**.
3. Under Related Links click **Advanced view**.
4. Go to the **Dependent Field** section.
5. Enable **Use dependent field**.
6. In **Dependent on field** select **Category**.
7. Save the form.
8. Scroll down to the **Choices** section.
9. For each Subcategory choice, set the Dependent value to the Category's backend name:

| Subcategory | Dependent on Category |
|---|---|
| Wi-Fi | Network |
| Projector | Hardware |
| Forgot Password | Access |
| Slow Computer | Performance |

10. Save the form. Now each Subcategory shows only for its matching Category.
