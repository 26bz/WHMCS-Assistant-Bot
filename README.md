# WHMCS-Assistant-Bot

Thank you for purchasing WHMCS-Assistant-Bot! Follow the guide below to get your bot up and running.

## Requirements

1. **Discord Bot Setup**: Make sure your Discord bot is created through the Discord Developer Portal. If you're unfamiliar with this, refer to the [Discord Bot Setup Guide](https://discord.com/developers/docs/quick-start/getting-started).

2. **Obtain Bot Credentials**: Collect the necessary credentials (bot token, client ID, etc.) and ensure they are added to your `.env` file.

3. **WHMCS API IP Whitelist**: 
   - Go to your WHMCS dashboard: **System Settings** → **General Settings** → **Security**.
   - Add your bot's IP address to the **API IP Access Restriction** section to authorize its use of the API.

4. **WHMCS API Access Key**: 
   - Set up an API access key for WHMCS following [this guide](https://developers.whmcs.com/api/access-control/).
   - Add the `WHMCS_API_ACCESS_KEY` to your `.env` file.

5. **Explore Commands Names**: The available bot commands names can seen in the `commands` folder. 

6. **Configure WHMCS API**:
   - In your WHMCS admin dashboard, go to **System Settings** → **API Credentials** → **API Roles**.
   - Click **Create a New Role**, name it, and optionally add a description.
   - Define which API actions this role is allowed to perform. Leave unchecked any actions you want to disallow.
   - Click **Save**.

7. **Generate API Credentials**:
   - Go to the **API Credentials** tab and click **Generate New API Credential**.
   - Select the admin user, add a description, and choose the role you just created.
   - Click **Generate**.

8. **Copy API Credentials**: You will receive the following credentials:
   - `WHMCS_API_IDENTIFIER=`
   - `WHMCS_API_SECRET=`
   
   Add these keys to your `.env` file.

9. **Set API URL**: Ensure that the WHMCS API URL in your `.env` file is set to:  
   ```
   WHMCS_API_URL=https://billing.example.com/includes/api.php
   ```

## Additional Configurations

In the `utils/config.json` file, ensure the following values are updated:

- `botOwnerIds: [""],` // Replace with actual owner IDs
- `adminIds: ["ADMIN_ID_1", "ADMIN_ID_2"],` // Replace with actual admin IDs
- `moderatorIds: ["MODERATOR_ID_1", "MODERATOR_ID_2"],` // Replace with actual moderator IDs

### Command Permission Levels

Each command file has a `permissionLevel` setting. The permission levels are:

- `1`: Owner (highest level)
- `2`: Admin
- `3`: Moderator (lowest level)

Users with a lower number (`1` or `2`) can execute commands set to a higher permission level (`3`). Adjust these based on your operational needs in the config.json.


## Running the Bot

To start the bot, use the following command:

```bash
node src/bot.js
```
