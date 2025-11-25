# Event Sentinel - Discord Event Logger Bot

A professional, production-ready Discord bot that logs all major server events using rich, detailed embeds.

## Features

### Event Logging Categories

#### 🔨 Moderation Events
- Member Banned / Unbanned
- Member Kicked
- Member Joined / Left
- Nickname Changed
- Timeout Given / Removed
- Role Added / Removed

#### 🎙️ Voice Events
- Member Joined/Left Voice Channel
- Member Moved Between Channels
- Member Muted / Unmuted
- Member Deafened / Undeafened

#### 📝 Message Events
- Message Deleted (with content and attachments)
- Message Edited (with before/after content)

#### 🧩 Channel & Thread Events
- Channel Created / Deleted / Updated
- Thread Created / Deleted / Updated
- Channel Permissions Updated

#### 🎨 Role Events
- Role Created / Deleted / Updated
- Role permissions and settings changes

#### ⚙️ Server Events
- Server Settings Updated
- Invite Created / Deleted

## Setup Instructions

### 1. Discord Bot Setup

1. Go to [Discord Developer Portal](https://discord.com/developers/applications)
2. Click "New Application" and give it a name
3. Go to the "Bot" section and click "Add Bot"
4. Under "Privileged Gateway Intents", enable:
   - Presence Intent
   - Server Members Intent
   - Message Content Intent
5. Copy your bot token

### 2. Bot Installation

1. Create a `.env` file based on `.env.example`:
   ```bash
   cp .env.example .env
   ```

2. Add your bot token to the `.env` file:
   ```
   DISCORD_TOKEN=your_bot_token_here
   ```

3. Create configuration files:
   ```bash
   # For simple config (optional)
   cp config.example.json config.json
   
   # OR for modular config (recommended)
   cp -r config.example config
   ```

4. Install dependencies:
   ```bash
   pip install discord.py python-dotenv PyNaCl
   ```

### 3. Invite Bot to Server

Generate an invite URL with these permissions:
- View Channels
- Send Messages
- Embed Links
- Attach Files
- Read Message History
- View Audit Log
- Manage Webhooks (optional)

Required scopes: `bot`, `applications.commands`

Invite URL template:
```
https://discord.com/api/oauth2/authorize?client_id=YOUR_BOT_CLIENT_ID&permissions=412385476672&scope=bot%20applications.commands
```

### 4. Configure Log Channel

Once the bot is running:
1. Use the `/setlogchannel` command in your Discord server (must be an administrator)
2. Select the channel where you want events to be logged for that specific server
3. Make sure the bot has permission to send messages in that channel
4. If you add the bot to multiple servers, repeat this command in each server to set up logging

**Note:** Each server has its own independent log channel configuration!

## Running the Bot

```bash
python main.py
```

The bot will start and display:
- Bot username and ID
- Discord.py version
- Current log channel (if configured)

## Configuration

### Configuration

The bot supports two configuration layouts. The loader prefers the modular `config/` layout if present, and falls back to the legacy `config.json`.

#### Preferred: config/ directory (modular)

Files (all optional):
- `config/base.json`: global defaults
- `config/colors.json`: embed colors map
- `config/guilds.json`: per-guild log channels
- `config/toggles.json`: per-guild event toggles

Example files:

`config/colors.json`
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

`config/guilds.json`
```json
{
  "123456789012345678": 987654321098765432
}
```

`config/toggles.json`
```json
{
  "123456789012345678": {
    "voice": { "self_unmute": false }
  }
}
```

#### Legacy: config.json (monolithic)

You may keep a single `config.json` with the combined structure. The bot will still read it if `config/` is absent. The application also mirrors the composed configuration back to `config.json` when saving, for compatibility.

**Multi-Guild Support:** The bot fully supports multiple Discord servers! Each server can have its own dedicated log channel, configured independently using `/setlogchannel`.

## Commands

- `/setlogchannel <channel>` - Set the log channel (Admin only)

## Embed Design

Each event type has a unique:
- Color scheme for quick visual identification
- Emoji icon for the event category
- Detailed fields with relevant information
- Timestamp of when the event occurred
- Moderator information (when available from audit logs)

## Architecture

The bot uses a modular cog-based structure:

```
event-sentinel/
├── main.py              # Bot initialization and startup
├── utils.py             # Shared utility functions
├── config.json          # Bot configuration
├── cogs/
│   ├── moderation.py    # Member and moderation events
│   ├── voice.py         # Voice channel events
│   ├── message.py       # Message events
│   ├── server.py        # Server and invite events
│   ├── roles.py         # Role events
│   └── channels.py      # Channel and thread events
```

## Requirements

- Python 3.11+
- discord.py 2.4+
- python-dotenv
- PyNaCl

## Permissions Required

The bot needs these permissions to function properly:
- View Audit Log (to capture moderator information)
- View Channels
- Send Messages
- Embed Links
- Read Message History

## Error Handling

The bot gracefully handles:
- Missing permissions
- Missing audit log entries
- Unavailable log channels
- Rate limiting

Errors are logged to console for debugging.

## Support

For issues or questions, please check:
1. Bot has correct permissions in the server
2. All required intents are enabled in the Developer Portal
3. Log channel is properly configured with `/setlogchannel`
4. Bot has permission to send messages in the log channel
