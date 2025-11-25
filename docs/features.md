---
layout: default
title: Features
nav_order: 3
---

# Event Sentinel Features

Event Sentinel provides comprehensive logging for all major Discord server events. Each event type is logged with rich, detailed embeds that make it easy to track and review server activity.

## Event Categories

### 🔨 Moderation Events

Track all moderation actions performed in your server:

- **Member Banned** - Logs when a member is banned, including reason and moderator
- **Member Unbanned** - Logs when a ban is removed
- **Member Kicked** - Tracks member removals with moderator information
- **Member Joined** - Welcome new members with join logs
- **Member Left** - Track when members leave the server
- **Nickname Changed** - Monitor nickname changes (self and admin changes)
- **Timeout Given** - Log when members are timed out
- **Timeout Removed** - Track timeout removals
- **Role Added** - Monitor role assignments
- **Role Removed** - Track role removals

**Color:** Red (`#E74C3C`)

### 🎙️ Voice Events

Comprehensive voice channel activity tracking:

- **Member Joined Voice Channel** - Track when members join voice channels
- **Member Left Voice Channel** - Log voice channel departures
- **Member Moved Between Channels** - Monitor channel switches
- **Member Muted** - Track when members are muted (self or server mute)
- **Member Unmuted** - Log unmute events
- **Member Deafened** - Monitor deafening actions
- **Member Undeafened** - Track undeafen events

**Color:** Purple (`#9B59B6`)

### 📝 Message Events

Detailed message activity logging:

- **Message Deleted** - Logs deleted messages with:
  - Full message content (if available)
  - Author information
  - Channel location
  - Attachment information
  - Deletion timestamp
- **Message Edited** - Tracks message edits with:
  - Original message content
  - Edited message content
  - Author information
  - Edit timestamp
  - Channel location

**Color:** Green (`#2ECC71`)

### 🧩 Channel & Thread Events

Monitor channel and thread management:

- **Channel Created** - Log new channel creation
- **Channel Deleted** - Track channel deletions
- **Channel Updated** - Monitor channel setting changes:
  - Name changes
  - Topic updates
  - Permission changes
  - Category changes
- **Thread Created** - Track thread creation
- **Thread Deleted** - Log thread deletions
- **Thread Updated** - Monitor thread changes
- **Channel Permissions Updated** - Detailed permission change logs

**Color:** Blue (`#3498DB`)

### 🎨 Role Events

Comprehensive role management tracking:

- **Role Created** - Log new role creation
- **Role Deleted** - Track role deletions
- **Role Updated** - Monitor role changes:
  - Name changes
  - Color changes
  - Permission modifications
  - Position changes
  - Hoist/mentionable settings

**Color:** Blue (`#3498DB`)

### ⚙️ Server Events

Track server-wide changes:

- **Server Settings Updated** - Monitor server configuration changes:
  - Server name changes
  - Icon updates
  - AFK channel changes
  - System channel updates
  - Verification level changes
  - Content filter updates
- **Invite Created** - Track invite link generation
- **Invite Deleted** - Log invite deletions

**Color:** Orange (`#F39C12`)

## Embed Design Features

### Visual Organization

Each event type features:

- **Color-Coded Categories** - Quick visual identification of event types
- **Emoji Icons** - Easy category recognition at a glance
- **Structured Fields** - Organized information presentation
- **Timestamps** - Precise event timing
- **Moderator Information** - When available from audit logs

### Rich Information Display

Event logs include:

- **User Information** - Avatar, username, and ID
- **Action Details** - What happened and when
- **Context** - Relevant channel, role, or server information
- **Before/After States** - For update events
- **Reason/Description** - Additional context when available

## Multi-Server Support

Event Sentinel fully supports multiple Discord servers:

- **Independent Configuration** - Each server has its own log channel
- **Per-Server Settings** - Customize logging per server
- **Isolated Data** - Server configurations are kept separate
- **Easy Management** - Configure each server independently

## Privacy & Security

- **Minimal Data Collection** - Only necessary data is stored
- **Local Storage** - Data stored in configuration files
- **No External Services** - Direct Discord API interaction only
- **Secure Handling** - No sensitive information in logs

## Performance Features

- **Efficient Logging** - Optimized event handling
- **Rate Limit Handling** - Graceful Discord API rate limit management
- **Error Recovery** - Continues operating even if individual events fail
- **Resource Efficient** - Low memory and CPU usage

## Customization Options

- **Configurable Colors** - Customize embed colors per category
- **Event Toggles** - Enable/disable specific event types per server
- **Flexible Configuration** - Modular or single-file configuration
- **Per-Guild Settings** - Different settings for different servers

## Reliability Features

- **Error Handling** - Graceful handling of missing permissions
- **Missing Data Handling** - Continues even if audit log entries are unavailable
- **Channel Availability** - Handles unavailable or deleted channels
- **Connection Recovery** - Automatic reconnection on network issues

---

**Want to customize these features?** Check out the [Configuration Guide]({{ site.baseurl }}/configuration/)!

