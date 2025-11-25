---
layout: default
title: Getting Started
nav_order: 2
---

# Getting Started with Event Sentinel

This guide will walk you through setting up Event Sentinel in your Discord server.

## Prerequisites

- Python 3.11 or higher
- A Discord account with server management permissions
- Basic familiarity with command-line interfaces

## Step 1: Discord Bot Setup

### Create a Discord Application

1. Go to the [Discord Developer Portal](https://discord.com/developers/applications)
2. Click **"New Application"** and give it a name (e.g., "Event Sentinel")
3. Navigate to the **"Bot"** section in the left sidebar
4. Click **"Add Bot"** and confirm

### Configure Bot Settings

1. Under **"Privileged Gateway Intents"**, enable:
   - ✅ **Presence Intent** - Required for tracking member presence
   - ✅ **Server Members Intent** - Required for member-related events
   - ✅ **Message Content Intent** - Required for logging message content

2. Copy your **Bot Token** (you'll need this later)
   - ⚠️ **Never share your bot token publicly!**

### Set Bot Permissions

The bot needs the following permissions to function properly:

- **View Channels** - To access channels
- **Send Messages** - To post log messages
- **Embed Links** - To create rich embeds
- **Attach Files** - To include attachments in logs
- **Read Message History** - To access message content
- **View Audit Log** - To identify moderators who performed actions
- **Manage Webhooks** (optional) - For enhanced logging capabilities

## Step 2: Install Event Sentinel

### Clone the Repository

```bash
git clone https://github.com/hugsndnugs/Event-Sentinel-bot-main.git
cd Event-Sentinel-bot-main
```

### Install Dependencies

```bash
pip install discord.py python-dotenv PyNaCl
```

Or using a requirements file (if available):

```bash
pip install -r requirements.txt
```

## Step 3: Configure the Bot

### Create Environment File

1. Create a `.env` file in the project root:

```bash
# Windows
copy .env.example .env

# Linux/Mac
cp .env.example .env
```

2. Add your bot token to the `.env` file:

```env
DISCORD_TOKEN=your_bot_token_here
```

### Set Up Configuration

Event Sentinel supports two configuration layouts:

#### Option 1: Modular Configuration (Recommended)

Create a `config/` directory with these files:

```bash
# Windows
mkdir config
copy config.example\* config\

# Linux/Mac
mkdir -p config
cp -r config.example/* config/
```

#### Option 2: Single Configuration File

```bash
# Windows
copy config.example.json config.json

# Linux/Mac
cp config.example.json config.json
```

See the [Configuration Guide]({{ site.baseurl }}/configuration/) for detailed configuration options.

## Step 4: Invite Bot to Your Server

### Generate Invite URL

Use this template, replacing `YOUR_BOT_CLIENT_ID` with your bot's Client ID (found in the Developer Portal under "General Information"):

```
https://discord.com/api/oauth2/authorize?client_id=YOUR_BOT_CLIENT_ID&permissions=412385476672&scope=bot%20applications.commands
```

Or use the [Discord Permission Calculator](https://discordapi.com/permissions.html) to generate a custom invite URL.

### Required Scopes

- `bot` - Basic bot functionality
- `applications.commands` - Slash command support

## Step 5: Configure Log Channel

Once the bot is in your server:

1. Run the bot (see Step 6)
2. Use the `/setlogchannel` command in your Discord server
   - You must be an administrator to use this command
3. Select the channel where you want events to be logged
4. Ensure the bot has permission to send messages in that channel

**Note:** Each server has its own independent log channel configuration. Repeat this step for each server you add the bot to.

## Step 6: Run the Bot

### Start the Bot

```bash
python main.py
```

You should see output like:

```
Event Sentinel is online!
Bot: Event Sentinel#1234 (123456789012345678)
Discord.py version: 2.4.0
```

### Running in Production

For production environments, consider using:

- **PM2** (Node.js process manager) - Can run Python scripts
- **systemd** (Linux) - For system service management
- **Screen/Tmux** - For persistent terminal sessions
- **Docker** - For containerized deployment

## Step 7: Verify Installation

Test that Event Sentinel is working:

1. **Check Bot Status** - The bot should appear online in your server
2. **Test Logging** - Perform a test action (e.g., change a nickname) and check your log channel
3. **Verify Permissions** - Ensure the bot can send messages in the log channel

## Troubleshooting

### Bot Doesn't Appear Online

- Check that the bot token is correct in `.env`
- Verify all required intents are enabled
- Check console for error messages

### No Logs Appearing

- Verify the log channel is set with `/setlogchannel`
- Check bot permissions in the log channel
- Ensure the bot has "View Audit Log" permission
- Check console for permission errors

### Missing Event Information

- Verify all required intents are enabled in Developer Portal
- Check that the bot has necessary permissions
- Some events require "View Audit Log" permission for moderator information

## Next Steps

- 📖 Learn about all [Features]({{ site.baseurl }}/features/)
- ⚙️ Customize your [Configuration]({{ site.baseurl }}/configuration/)
- 📝 Explore available [Commands]({{ site.baseurl }}/commands/)
- ❓ Check the [FAQ]({{ site.baseurl }}/faq/) for common questions

---

**Need help?** Visit our [Support]({{ site.baseurl }}/support/) page or [open an issue](https://github.com/hugsndnugs/Event-Sentinel-bot-main/issues) on GitHub.

