# Discourse restrict user status
This component restricts the ability of Discourse users to set user status to select groups, including forum staff, superusers, etc. If you have not yet enabled the user status setting, just install this theme component and configure it's settings.  Then go to admin-settings and enable the "enable user status" setting.

**Note**: If you have already enabled the user status setting and let a lot of users fill their user status, then you will need to do a rails command on user statuses to bulk reset them all to default blank setting (backup first anytime you do rails commmands!). If the number of users is not high, you may wish to simply impersonate to remove their respective statuses.

To bullk reset existing user statuses:
* Backup first!!
* SSH into your Discourse server.
* Enter the Discourse container: ./launcher enter app
* Enter the Rails console: rails c
* Run the following commands:
* UserStatus.update_all(emoji: '', description: '')
This will set the emoji and description fields to an empty string for all users, effectively resetting their statuses.
