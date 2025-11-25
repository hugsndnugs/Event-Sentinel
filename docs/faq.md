---
layout: default
title: FAQ
nav_order: 6
---

# Frequently Asked Questions

Common questions and answers about Event Sentinel.

## General Questions

### What is Event Sentinel?

Event Sentinel is a Discord bot that logs all major server events using rich, detailed embeds. It helps server administrators maintain comprehensive records of server activity, including moderation actions, message changes, voice activity, and more.

### Is Event Sentinel free?

Yes! Event Sentinel is open source and free to use. You can host it yourself or use a hosted instance if available.

### Do I need to host Event Sentinel myself?

Yes, Event Sentinel is a self-hosted bot. You'll need to run it on your own server or computer. See the [Getting Started Guide]({{ site.baseurl }}/getting-started/) for setup instructions.

### Can I use Event Sentinel in multiple servers?

Yes! Event Sentinel fully supports multiple Discord servers. Each server can have its own independent log channel and configuration.

## Setup & Installation

### What are the system requirements?

- Python 3.11 or higher
- Internet connection
- Discord account with server management permissions
- Basic command-line knowledge

### Do I need to enable any special Discord intents?

Yes, you need to enable these Privileged Gateway Intents in the Discord Developer Portal:
- Presence Intent
- Server Members Intent
- Message Content Intent

### What permissions does the bot need?

The bot needs these permissions:
- View Channels
- Send Messages
- Embed Links
- Attach Files
- Read Message History
- View Audit Log

See the [Getting Started Guide]({{ site.baseurl }}/getting-started/) for detailed setup instructions.

### How do I get my bot token?

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Select your application
3. Go to the "Bot" section
4. Click "Reset Token" or copy the existing token
5. ⚠️ **Never share your token publicly!**

## Configuration

### How do I set the log channel?

Use the `/setlogchannel` command in your Discord server. You must be an administrator to use this command.

### Can I have different log channels for different event types?

Currently, all events are logged to a single channel per server. This may be added in future updates.

### How do I customize embed colors?

Edit the `config/colors.json` file (or `config.json` if using single-file config). See the [Configuration Guide]({{ site.baseurl }}/configuration/) for details.

### Can I disable certain event types?

Yes! You can configure event toggles in `config/toggles.json`. See the [Configuration Guide]({{ site.baseurl }}/configuration/) for examples.

## Usage

### Why aren't events being logged?

Check these common issues:
1. **Log channel not set** - Use `/setlogchannel` to configure
2. **Missing permissions** - Bot needs "Send Messages" in the log channel
3. **Missing intents** - Verify all required intents are enabled
4. **Bot offline** - Ensure the bot is running
5. **Event toggled off** - Check `config/toggles.json`

### Why can't I see moderator information?

The bot needs "View Audit Log" permission to identify moderators. Without this permission, events will still be logged but moderator information may be missing.

### Can I see deleted message content?

Yes! If the bot has Message Content Intent enabled and the message was cached, deleted message content will be included in the log.

### How long are logs kept?

Logs are sent to Discord channels, so they follow Discord's message retention policies. The bot itself doesn't store historical logs.

## Troubleshooting

### The bot appears offline

1. Check that the bot is running (`python main.py`)
2. Verify the bot token in `.env` is correct
3. Check console/terminal for error messages
4. Ensure all required intents are enabled

### Commands don't appear

1. Re-invite the bot with `applications.commands` scope
2. Wait a few minutes for commands to sync (can take up to an hour)
3. Restart the bot

### "Permission denied" errors

- Verify bot has necessary permissions in the server
- Check bot has permission in the specific channel
- Ensure "View Audit Log" permission is granted for moderator info

### Bot crashes or stops working

1. Check console/terminal for error messages
2. Verify Python version (3.11+)
3. Ensure all dependencies are installed
4. Check Discord API status
5. Review configuration files for syntax errors

### Events are missing information

- Some events require "View Audit Log" for full details
- Message content requires Message Content Intent
- Some information may not be available from Discord's API

## Privacy & Security

### What data does Event Sentinel collect?

Event Sentinel collects minimal data:
- Discord Server IDs
- Log Channel IDs
- Event details (for logging purposes)

No personal information (names, emails, IP addresses) is collected. See the [Privacy Policy]({{ site.baseurl }}/privacy-policy/) for details.

### Where is data stored?

Data is stored locally in configuration files on the host machine. It's not sent to external services or databases.

### Is my data secure?

Yes. Event Sentinel only interacts with Discord's API and stores data locally. No data is shared, sold, or used for marketing.

### Can I delete my data?

Yes. Removing the bot from your server removes access to your server's data. You can also manually delete configuration entries or contact the developer for assistance.

## Technical Questions

### What version of Python do I need?

Python 3.11 or higher is required.

### What Discord.py version is used?

Event Sentinel uses discord.py 2.4 or higher.

### Can I modify the bot code?

Yes! Event Sentinel is open source. You can modify it to suit your needs. However, please respect the license terms.

### How do I update Event Sentinel?

1. Pull the latest changes from the repository
2. Update dependencies: `pip install -r requirements.txt --upgrade`
3. Restart the bot

### Does the bot work with Discord.py 1.x?

No, Event Sentinel requires discord.py 2.4 or higher.

## Support

### Where can I get help?

- 📖 Check the [Documentation]({{ site.baseurl }}/getting-started/)
- ❓ Review this FAQ
- 🐛 [Open an issue](https://github.com/hugsndnugs/Event-Sentinel-bot-main/issues) on GitHub
- 💬 Visit the [Support]({{ site.baseurl }}/support/) page

### How do I report a bug?

1. Check if the issue is already reported on GitHub
2. Create a new issue with:
   - Description of the problem
   - Steps to reproduce
   - Expected vs. actual behavior
   - Error messages (if any)
   - Your configuration (without sensitive data)

### Can I contribute to Event Sentinel?

Yes! Contributions are welcome. Please check the repository for contribution guidelines.

---

**Still have questions?** Visit our [Support]({{ site.baseurl }}/support/) page or [open an issue](https://github.com/hugsndnugs/Event-Sentinel-bot-main/issues) on GitHub.

