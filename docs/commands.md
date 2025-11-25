---
layout: default
title: Commands
nav_order: 5
---

# Event Sentinel Commands

Event Sentinel uses Discord slash commands for easy interaction. All commands are context-aware and provide helpful information.

## Available Commands

### `/setlogchannel`

Sets the log channel for the current server where all events will be logged.

**Usage:**
```
/setlogchannel <channel>
```

**Parameters:**
- `channel` (required) - The channel where events should be logged

**Permissions:**
- Requires **Administrator** permission

**Example:**
```
/setlogchannel #mod-logs
```

**Notes:**
- Each server has its own independent log channel configuration
- The bot must have permission to send messages in the selected channel
- You can change the log channel at any time by running this command again
- The channel must be visible to the bot

**What Happens:**
- The bot will immediately start logging events to the specified channel
- Previous log channel configuration is overwritten
- Configuration is saved automatically

## Command Permissions

### Administrator Commands

- `/setlogchannel` - Requires Administrator permission

**Why Administrator?**
- Log channel configuration is a sensitive setting
- Prevents unauthorized users from changing where logs are sent
- Ensures only trusted server staff can configure logging

## Using Commands

### How to Use Slash Commands

1. Type `/` in any channel where the bot has access
2. Start typing the command name (e.g., `setlogchannel`)
3. Select the command from the autocomplete menu
4. Fill in required parameters
5. Press Enter to execute

### Command Autocomplete

Discord provides helpful autocomplete for:
- Channel selection (for `/setlogchannel`)
- Parameter suggestions
- Command descriptions

## Troubleshooting Commands

### Command Not Appearing

**Possible Causes:**
- Bot hasn't been invited with `applications.commands` scope
- Commands are still syncing (can take up to an hour)
- Bot is offline

**Solutions:**
1. Re-invite the bot with the correct scopes:
   ```
   https://discord.com/api/oauth2/authorize?client_id=YOUR_BOT_ID&permissions=412385476672&scope=bot%20applications.commands
   ```
2. Wait a few minutes for commands to sync
3. Restart the bot if it's running

### Permission Denied

**Error:** "You don't have permission to use this command"

**Solution:**
- Ensure you have Administrator permission in the server
- Check your role hierarchy if using role-based permissions

### Channel Not Found

**Error:** "Channel not found" or channel doesn't appear in autocomplete

**Possible Causes:**
- Bot doesn't have access to the channel
- Channel is in a category the bot can't see
- Channel ID is incorrect

**Solutions:**
1. Ensure bot has "View Channels" permission
2. Check channel visibility settings
3. Use the channel mention or autocomplete instead of manual ID entry

### Command Not Working

**General Troubleshooting:**
1. Check bot is online and responsive
2. Verify bot has necessary permissions
3. Check console/terminal for error messages
4. Ensure you're using the command in the correct server
5. Try restarting the bot

## Command Best Practices

### Setting Up Log Channels

1. **Create a Dedicated Channel**
   - Create a channel specifically for logs (e.g., `#mod-logs`, `#event-logs`)
   - Set appropriate permissions (read-only for most users)
   - Pin important information if needed

2. **Configure Early**
   - Set the log channel as soon as the bot is added
   - Test with a simple action to verify logging works

3. **Multiple Servers**
   - Remember to configure each server independently
   - Use descriptive channel names to avoid confusion

### Security Considerations

- Only grant Administrator permission to trusted users
- Regularly audit who has access to log channels
- Consider using role-based permissions for additional security

## Future Commands

Additional commands may be added in future updates:

- `/toggleevent` - Enable/disable specific event types
- `/logchannel` - View current log channel
- `/config` - View or modify configuration
- `/help` - Display command help

**Note:** These are potential future features and may not be available yet.

## Command Support

If you encounter issues with commands:

1. Check the [FAQ]({{ site.baseurl }}/faq/) for common issues
2. Visit the [Support]({{ site.baseurl }}/support/) page
3. [Open an issue](https://github.com/hugsndnugs/Event-Sentinel/issues) on GitHub

---

**Need help?** Check out the [Getting Started Guide]({{ site.baseurl }}/getting-started/) or [FAQ]({{ site.baseurl }}/faq/).

