# Slack

**SLACK PLUGIN - CLOUD**

1. Sign in the slack or create account with [https://slack.com/signin#/signin](https://slack.com/signin#/signin)
2. Create a workspace if you do not have one. [https://slack.com/signin#/workspaces](https://slack.com/signin#/workspaces)
3. Go to [https://api.slack.com/](https://api.slack.com) and click **Create a custom app**![](../../.gitbook/assets/2)
4. Give your app a name and select the workspace you want to use.

![](<../../.gitbook/assets/3 (3)>)

1. Go to **Settings** -> **Manage Distribution** page. Under the **Share Your App with Other Workspaces** enable **Bots** and **Permissions**.

![](<../../.gitbook/assets/4 (2)>)

1. Go to **Features -> OAuth & Permissions**. Under the **Scopes** section, add the necessary OAuth scopes to **Bot Token Scopes.** These are channels:read, chat:write or chat:write.public according to your preference, usergroups:read, users.profile:read, users:read.

![](../../.gitbook/assets/5)

1. From the same page, click **Reinstall to Workspace** button under the **OAuth Tokens & Redirect URLs** section for changes you made to take effect.

![](<../../.gitbook/assets/6 (2)>)

1. Copy your **Bot User OAuth Access Token**. Go to [Testinium](https://testinium.io).
2. Go to **Account Information**

![](<../../.gitbook/assets/7 (1)>)

1. Go to **Plugins.** Click the Edit button of the **Slack Plugin.**

![](<../../.gitbook/assets/8 (1)>)

1. Paste the **OAuth Access Token** you have copied into the **SLACK API TOKEN\*** box.

![](<../../.gitbook/assets/9 (2)>)

1. Click **SAVE** and go to the suite you want to use with Slack Plugin. Click **Edit**.

![](<../../.gitbook/assets/10 (2)>)

1. Go to **SCHEDULE & NOTIFICATIONS** section. Enable **Notifications** if it is not.

![](../../.gitbook/assets/11)

1. Select Slack as your **Notification Type.** In the **Slack\*** box, give **@username** if you want to send Slack notification to an user otherwise give **#channelname** to send Slack notification to a channel.
2. Select **Execution Status** you wish and click the **ADD** button.
3. Click **APPLY** and **SAVE** and run your Suite. According to your Execution Status, Slack notification should be received.

![](<../../.gitbook/assets/12 (1)>)

![](<../../.gitbook/assets/13 (1)>)
