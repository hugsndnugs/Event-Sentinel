---
layout: default
title: Configuration
nav_order: 4
---

# Configuration Guide

Event Sentinel supports flexible configuration options to customize logging behavior for your server(s).

## Configuration Layouts

Event Sentinel supports two configuration approaches:

### Option 1: Modular Configuration (Recommended)

The bot prefers a modular `config/` directory structure if present. This makes it easier to manage settings for multiple servers.

### Option 2: Single Configuration File

A single `config.json` file is also supported for simpler setups.

## Modular Configuration Structure

Create a `config/` directory with these optional files:

```
config/
├── base.json      # Global defaults
├── colors.json    # Embed colors map
├── guilds.json    # Per-guild log channels
└── toggles.json   # Per-guild event toggles
```

### base.json

Global default settings (optional):

```json
{
  "default_log_channel": null,
  "default_color": "0x3498DB"
}
```

### colors.json

Customize embed colors for each event category:

```json
{
  "moderation": "0xE74C3C",
  "channel": "0x3498DB",
  "voice": "0x9B59B6",
  "message": "0x2ECC71",
  "server": "0xF39C12",
  "role": "0x3498DB"
}
```

**Color Format:** Use hexadecimal color codes with `0x` prefix (e.g., `0xE74C3C` for red).

**Available Categories:**
- `moderation` - Moderation events (bans, kicks, etc.)
- `channel` - Channel and thread events
- `voice` - Voice channel events
- `message` - Message events
- `server` - Server-wide events
- `role` - Role events

### guilds.json

Configure log channels for each server:

```json
{
  "123456789012345678": 987654321098765432,
  "876543210987654321": 111222333444555666
}
```

**Format:** `"Guild ID": Channel ID`

**How to Find IDs:**
1. Enable Developer Mode in Discord (User Settings → Advanced → Developer Mode)
2. Right-click on your server → Copy Server ID
3. Right-click on a channel → Copy Channel ID

### toggles.json

Enable or disable specific events per server:

```json
{
  "123456789012345678": {
    "voice": {
      "self_unmute": false
    },
    "moderation": {
      "nickname_change": true
    }
  }
}
```

**Available Toggle Categories:**
- `voice` - Voice event toggles
- `moderation` - Moderation event toggles
- `message` - Message event toggles
- `channel` - Channel event toggles
- `role` - Role event toggles
- `server` - Server event toggles

## Single Configuration File (config.json)

If you prefer a single file, use this structure:

```json
{
  "guilds": {
    "123456789012345678": 987654321098765432
  },
  "colors": {
    "moderation": "0xE74C3C",
    "channel": "0x3498DB",
    "voice": "0x9B59B6",
    "message": "0x2ECC71",
    "server": "0xF39C12",
    "role": "0x3498DB"
  },
  "toggles": {
    "123456789012345678": {
      "voice": {
        "self_unmute": false
      }
    }
  }
}
```

## Environment Variables

### .env File

Create a `.env` file in the project root:

```env
DISCORD_TOKEN=your_bot_token_here
```

**Security Note:** Never commit your `.env` file to version control. Add it to `.gitignore`.

## Configuration Priority

1. **Command Configuration** - `/setlogchannel` command (highest priority)
2. **Modular Config** - `config/` directory files
3. **Legacy Config** - `config.json` file
4. **Defaults** - Built-in bot defaults

## Multi-Server Configuration

Event Sentinel fully supports multiple servers with independent configurations:

### Setting Up Multiple Servers

1. **Add Bot to Server** - Invite the bot to each server
2. **Set Log Channel** - Use `/setlogchannel` in each server
3. **Customize Settings** - Configure colors and toggles per server in `config/` files

### Example: Two Servers

```json
// config/guilds.json
{
  "111111111111111111": 222222222222222222,
  "333333333333333333": 444444444444444444
}

// config/toggles.json
{
  "111111111111111111": {
    "voice": {
      "self_unmute": false
    }
  },
  "333333333333333333": {
    "message": {
      "edit": false
    }
  }
}
```

## Configuration Best Practices

### Security

- ✅ Keep `.env` file secure and never share it
- ✅ Don't commit sensitive data to version control
- ✅ Use environment variables for tokens

### Organization

- ✅ Use modular config for multiple servers
- ✅ Document custom configurations
- ✅ Keep backup of configuration files

### Performance

- ✅ Only enable events you need
- ✅ Use toggles to disable noisy events
- ✅ Monitor log channel activity

## Updating Configuration

### Via Command

The easiest way to update log channels:

```
/setlogchannel #your-log-channel
```

### Via Files

1. Edit the appropriate config file
2. Save the file
3. Restart the bot (if required)

**Note:** Some changes may require a bot restart. Check the bot's behavior after making changes.

## Troubleshooting Configuration

### Bot Not Reading Config

- Verify file syntax (valid JSON)
- Check file paths are correct
- Ensure bot has read permissions
- Restart the bot after changes

### Wrong Log Channel

- Verify channel ID is correct
- Check bot has access to the channel
- Use `/setlogchannel` to reset

### Colors Not Working

- Verify color format (`0x` prefix)
- Check color codes are valid hex
- Ensure JSON syntax is correct

### Events Not Logging

- Check event toggles in `toggles.json`
- Verify bot permissions
- Ensure required intents are enabled
- Check log channel is set correctly

## Configuration Examples

### Minimal Setup

```json
// config/guilds.json
{
  "YOUR_GUILD_ID": "YOUR_CHANNEL_ID"
}
```

### Full Customization

```json
// config/colors.json
{
  "moderation": "0xFF0000",
  "channel": "0x0000FF",
  "voice": "0xFF00FF",
  "message": "0x00FF00",
  "server": "0xFFFF00",
  "role": "0x00FFFF"
}

// config/guilds.json
{
  "111111111111111111": 222222222222222222
}

// config/toggles.json
{
  "111111111111111111": {
    "voice": {
      "self_unmute": false,
      "self_deafen": false
    },
    "moderation": {
      "nickname_change": true
    }
  }
}
```

---

**Need help with configuration?** Check the [FAQ]({{ site.baseurl }}/faq/) or [Support]({{ site.baseurl }}/support/) page.

