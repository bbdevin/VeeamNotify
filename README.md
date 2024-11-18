
# VeeamNotify

![{13A74740-2515-4007-94F4-6A0488779A14}](https://github.com/user-attachments/assets/e7b00ba8-4347-42f2-924d-ece0102594a5)

VeeamNotify now supports sending Veeam Backup & Replication session summary notifications to **Mattermost**! Configure your `config.json` with a Mattermost Webhook URL to receive detailed backup job results and status updates in your Mattermost channel.

---

## Supported Notification Services

VeeamNotify supports the following platforms:
* Discord
* Slack
* Microsoft Teams
* Telegram
* **Mattermost** (newly added!)

---

## Mattermost Configuration

To enable Mattermost notifications, follow these steps:

1. Edit the configuration file located at `C:\VeeamScripts\VeeamNotify\config\conf.json`.
2. Add your Mattermost Webhook URL under the `mattermost` section as shown below:

```json
"mattermost": {
    "webhook": "https://your-mattermost-url/hooks/your-webhook-id"
}
```

Once configured, notifications will be sent to your Mattermost channel in a professional format, including details such as job name, status, backup size, transfer size, and duration.

---

## Example Notification (Mattermost)

Here’s an example of how a Mattermost notification will look:

```
Veeam Job: BACKUP_PERSONNEL_SYSTEM (Incremental)
Status: Success
Job Type: Backup
Data Size: 0.02 GB
Transferred Data: 0.01 GB
Duration: 3m 33s
Start Time: 2024-11-15 17:00:42
End Time: 2024-11-15 17:04:16
```

The notification will also include any additional fields or details relevant to the backup job.

---

## Installation

1. Place the entire project in the directory `C:\VeeamScripts\VeeamNotify`.
2. In the Veeam Backup & Replication job settings, configure the post-job script with the following command:

   ```plaintext
   Powershell.exe -File C:\VeeamScripts\VeeamNotify\Bootstrap.ps1
   ```

3. Edit the `config.json` file located in `C:\VeeamScripts\VeeamNotify\config` to configure notification services and webhook URLs.
### Requirements:
* Veeam Backup & Replication 11 or higher.
* PowerShell 5.1 or higher.

For installation instructions, refer to the [How to Install](https://github.com/tigattack/VeeamNotify/wiki/%F0%9F%94%A7-How-to-Install) wiki page.

---

## Acknowledgments

This project is based on the work of tigattack, with contributions from various collaborators. See the original project's credits for more details.
