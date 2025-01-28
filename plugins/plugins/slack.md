# Slack

**SLACK PLUGIN - CLOUD**

1. Sign in to Slack or create an account at [**Slack Sign-In**](https://slack.com/signin#/signin).
2. If you do not already have a workspace, create one at [**Slack Workspaces**](https://slack.com/signin#/workspaces).
3. Navigate to [**Slack API Apps**](https://api.slack.com/apps) and click **Create New App**.

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 21.48.01.png" alt=""><figcaption></figcaption></figure>

4. Select **From Scratch** on the **Create an App** pop-up.

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 21.48.31.png" alt=""><figcaption></figcaption></figure>

5. Enter a name for your app, select the workspace you want to use, and click the **Create App** button.

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 21.36.52.png>)

6. Navigate to **Features** -> **OAuth & Permissions**.\
   Under the **Scopes** section, add the required OAuth scopes to **Bot Token Scopes**. The necessary scopes are:
   * `channels:read`
   * `chat:write` or `chat:write.public`
   * `usergroups:read`
   * `users.profile:read`
   * `users:read`

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 21.56.33.png" alt=""><figcaption></figcaption></figure>

7. Navigate to **Settings** - **Manage Distribution**. Under the **Share Your App with Other Workspaces** section, enable **Bots** and **Permissions**.

<figure><img src="../../.gitbook/assets/Screenshot 2025-01-28 at 21.54.15 (1).png" alt=""><figcaption></figcaption></figure>

8. On the same page, under the **OAuth Tokens & Redirect URLs** section, click the **Install to Workspace** button to apply the changes you made.

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 21.58.55.png>)

9. Copy your **Bot User OAuth Access Token**. Then, navigate to **Testinium** and go to the **Account Information** page.

![](<../../.gitbook/assets/Screenshot 2025-01-27 at 15.29.23 (1).png>)

10. Navigate to the **Plugins** tab and click the **Edit** button for the Slack Plugin.

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 22.04.10 (1).png>)

11. Paste the **OAuth Access Token** you copied into the **SLACK API TOKEN** box.

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 22.06.34.png>)

12. Click **Save**, then navigate to the **Plan** you want to use with the Slack Plugin. Click **Edit** button.

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 22.38.50.png>)

13. Navigate to the **SCHEDULE & NOTIFICATIONS** section. Enable **Notifications** if it is not already enabled. Select **Slack** as your **Notification Type**.

    In the **Slack** box:

    * Enter **@username** to send the Slack notification to a specific user.
    * Enter **#channelname** to send the Slack notification to a specific channel.

    Select the desired **Execution Status** for notifications and click the **Add** button. Then, click **Apply** and **Save** buttons.

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 22.36.45.png>)

&#x20;14\. Run your test plan. Based on the selected **Execution Status**, a Slack notification will be sent and should be received.

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 22.40.01.png>)

![](<../../.gitbook/assets/Screenshot 2025-01-28 at 22.46.35.png>)
