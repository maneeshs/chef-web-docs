=====================================================
Send Chef Automate Visibility notifications to Slack
=====================================================
`[edit on GitHub] <https://github.com/chef/chef-web-docs/blob/master/chef_master/source/integrate_notifications_slack.rst>`__

.. tag chef_automate_mark

.. image:: ../../images/chef_automate_full.png
   :width: 40px
   :height: 17px

.. end_tag

Chef Automate may be configured to notify a particular slack channel or user when it detects certain issues with the nodes you are managing.
Currently, those issues include:

* A Chef client run failure on any node in your fleet.
* An Inspec compliance scan failure on any node in your fleet.

Integrating Chef Automate with Slack requires a webhook to be created in Slack, and then saving that webhook in Chef Automate. Currently, any
user of Chef Automate may create and manage notifications. Notifications sent to slack by Chef Automate will respect any outbound proxy settings
that you may have configured in your `delivery.rb`.

.. note:: Notifications sent to Slack by Chef Automate do not support retries. Therefore, notifications sent while Slack is experiencing API issues, outages, or some other unplanned downtime may never be received by the channel. Undelivered notifications are not re-sent. Attempts to send notifications do generate log messages in your Chef Automate server.

Create a Webhook
=====================================================
To create a webhook in Slack:

#. `Create an incoming webhook <https://slack.com/apps/A0F7XDUAZ-incoming-webhooks>`__ in Slack and be sure to use the team in Slack to be associated with Chef Automate.
#. Select a team, and then click the **Configure** button.
#. Select **Add Configuration** (if that team already has at least one webhook) or **Install** to add a webhook.
#. Under **Post to Channel** select the channel in Slack to which Chef Automate will send notifications.
#. Click **Add Incoming Webhooks Integration**. Slack will create the new webhook, and then provide a location from which the URL for that webhook can be copied.
#. Copy the URL.

Add a Webhook to Chef Automate
=====================================================
To add a Slack webhook for Chef Automate:

#. On the Chef Automate server, select **Notifications** under the **Nodes** tab.
#. Click **Create Notification** and select **Add Slack notification** from the drop-down menu.
#. Pick the event you want to be notified about. Currently, you can choose to be notified on any Chef client run failures or any Inspec compliance scan failures.
#. Pick a meaningful name for the webhook, and then paste the Slack webhook URL from the previous section.
#. Click **Send a Test**. If a test notification is successful, click **Save**.

Edit Slack Notifications
=====================================================
To edit a Slack webhook for Chef Automate:

#. On the Chef Automate server, select **Notifications** under the **Nodes** tab.
#. Use the navigation bar at the bottom of the page if necessary to scroll through the list of all notifications.
#. Click the **Edit** button that looks like a pencil and change the appropriate fields.
#. Click **Save** to store your changes.

Delete Slack Notifications
=====================================================
To delete a Slack webhook for Chef Automate:

#. On the Chef Automate server, select **Notifications** under the **Nodes** tab.
#. Use the navigation bar at the bottom of the page if necessary to scroll through the list of all notifications.
#. Click the **Delete** button that looks like a red dust bin and confirm your intent to delete the notification.
