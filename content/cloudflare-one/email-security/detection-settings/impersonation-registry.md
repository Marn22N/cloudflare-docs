---
title: Impersonation registry
pcx_content_type: how-to
weight: 4
---

# Impersonation registry

The impersonation registry contains combinations of emails of users who are likely to be impersonated. If there is an email that is on the impersonation registry not listed as an alternative email address, that email will be reported as potential [business email compromise (BEC)](https://www.cloudflare.com/en-gb/learning/email-security/business-email-compromise-bec/).

{{<Aside type="note">}}

The impersonation registry should contain a list of users who are likely to be impersonated. Email Security applies enhanced security to variations of registered email addresses for additional [Business Email Compromise (BEC)](https://www.cloudflare.com/en-gb/learning/email-security/business-email-compromise-bec/) protection.

{{</Aside>}}

To add a user to the impersonation registry:

1. Log in to the [Cloudflare dashboard](https://dash.cloudflare.com/).
2. Select **Email Security**.
3. Select **Settings** > **Impersonation registry**.
4. Select **+ Add a user**.
5. Select **Input method**: Choose between **Manual input**, **Upload manual list**, and **Select from existing directories**:
   - **Manual input**: Enter the following information:
       - **User info**: enter a valid **Display name**.
       - **User email**: Enter one of the following:
         - **Email address**: Enter all known email addresses, separated by a comma.
         - **Regular expressions**: Must be valid Java expressions.
   - **Upload manual list**: You can upload a file no larger than 150 KB containing all variables of potential emails. The file must contain `Display_Name` and `Email`, and the first row must be the header row.
   - **Select from existing directories**:
       - **Select directory**: Select your directory.
       - **Add users or groups**: Choose the users or groups you want to register.
6. Select **Save**.

## Edit users

{{<Aside type="note">}}

Administrators can edit the names and emails of users who belong to the Email Security directory. Administrators from other integrated directories cannot edit the name and the primary emails of users.

{{</Aside>}}

To edit users from the Email Security directory:

1. Select the user you want to edit.
2. Select the three dots > **Edit**.
3. Enter the **Display name**, **Email** and **Secondary email**.
4. Select **Save**.

To edit users from other integrations:

1. Select the user you want to edit.
2. Select the three dots > **Edit**.
3. Enter the **Secondary email**.
4. Select **Save**.

## Remove users

{{<Aside type="note">}}

If you added a user to the impersonation registry, and the user was manually added to the Email Security directory, you cannot remove the user from the **Impersonation registry**. To remove the user:

1. Select **Directories** on the sidebar.
2. Select the directory where your user is allocated.
3. Select the **Users** tab.
4. Search for the user you want to remove.
5. Select the three dots > **Remove from registry**.

{{</Aside>}}

To remove a user from the impersonation registry:

1. Select the user you want to remove.
2. Select the three dots > **Remove from registry**.
3. Read the pop-up message, then select **Remove user**.

To remove multiple users at once from the impersonation registry:

1. Select all the users you want to remove.
2. Select **Action** > **Remove from registry**.
3. Read the pop-up message, then select **Remove users**.