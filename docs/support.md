---
layout: default
title: Support
nav_order: 7
---

# Support

Need help with Event Sentinel? We're here to assist you!

## Getting Help

### Documentation

Before reaching out, please check our comprehensive documentation:

- 📖 [Getting Started]({{ site.baseurl }}/getting-started/) - Setup and installation guide
- ✨ [Features]({{ site.baseurl }}/features/) - Learn what Event Sentinel can do
- ⚙️ [Configuration]({{ site.baseurl }}/configuration/) - Customize your setup
- 📝 [Commands]({{ site.baseurl }}/commands/) - Available commands reference
- ❓ [FAQ]({{ site.baseurl }}/faq/) - Common questions and answers

### Common Issues

Most issues can be resolved by checking:

1. **Bot Permissions** - Ensure the bot has all required permissions
2. **Intents** - Verify all Privileged Gateway Intents are enabled
3. **Log Channel** - Confirm the log channel is set with `/setlogchannel`
4. **Bot Status** - Check that the bot is online and running
5. **Configuration** - Review your configuration files for errors

## Reporting Issues

### Before Reporting

Please check:
- ✅ The [FAQ]({{ site.baseurl }}/faq/) for common solutions
- ✅ Existing [GitHub Issues](https://github.com/hugsndnugs/Event-Sentinel-bot-main/issues) for similar problems
- ✅ That you're using the latest version
- ✅ Your configuration and setup

### How to Report

When reporting an issue on GitHub, please include:

1. **Description** - Clear description of the problem
2. **Steps to Reproduce** - How to trigger the issue
3. **Expected Behavior** - What should happen
4. **Actual Behavior** - What actually happens
5. **Error Messages** - Any error messages or logs
6. **Environment**:
   - Python version
   - Discord.py version
   - Operating system
7. **Configuration** - Relevant config (without sensitive data like tokens)

### Issue Templates

When creating an issue on GitHub, use the appropriate template if available:
- 🐛 Bug Report
- 💡 Feature Request
- 📖 Documentation Request
- ❓ Question

## Contact Information

### Developer

- **Discord:** HugsNdNugs
- **GitHub:** [@hugsndnugs](https://github.com/hugsndnugs)

### Official Channels

- **GitHub Repository:** [Event-Sentinel-bot-main](https://github.com/hugsndnugs/Event-Sentinel-bot-main)
- **Issues:** [GitHub Issues](https://github.com/hugsndnugs/Event-Sentinel-bot-main/issues)
- **Discussions:** [GitHub Discussions](https://github.com/hugsndnugs/Event-Sentinel-bot-main/discussions) (if available)

## Troubleshooting Steps

### Bot Not Working

1. **Check Bot Status**
   ```bash
   # Verify bot is running
   python main.py
   ```

2. **Verify Configuration**
   - Check `.env` file has correct token
   - Verify `config.json` or `config/` files are valid JSON
   - Ensure log channel is set

3. **Check Permissions**
   - Bot has required permissions in server
   - Bot can send messages in log channel
   - Bot has "View Audit Log" permission

4. **Verify Intents**
   - All three Privileged Gateway Intents enabled
   - Bot application saved in Developer Portal

### Events Not Logging

1. **Log Channel**
   - Use `/setlogchannel` to set channel
   - Verify bot has access to channel

2. **Event Toggles**
   - Check `config/toggles.json` for disabled events
   - Verify event isn't toggled off

3. **Permissions**
   - Bot needs "View Audit Log" for some events
   - Message Content Intent for message events

### Commands Not Appearing

1. **Re-invite Bot**
   - Include `applications.commands` scope
   - Wait for commands to sync (up to 1 hour)

2. **Check Bot Status**
   - Ensure bot is online
   - Restart bot if needed

## Community Support

### Contributing

We welcome contributions! Ways to help:

- 🐛 Report bugs
- 💡 Suggest features
- 📖 Improve documentation
- 🔧 Submit pull requests
- ❓ Answer questions

### Guidelines

When seeking or providing support:

- ✅ Be respectful and patient
- ✅ Provide clear, detailed information
- ✅ Search for existing solutions first
- ✅ Follow the code of conduct
- ✅ Help others when you can

## Additional Resources

### External Resources

- [Discord.py Documentation](https://discordpy.readthedocs.io/)
- [Discord Developer Portal](https://discord.com/developers/applications)
- [Discord API Documentation](https://discord.com/developers/docs/)

### Learning Resources

- Python Discord bot tutorials
- Discord.py guides
- Discord API documentation

## Privacy & Data

For questions about:
- **Data Collection** - See [Privacy Policy]({{ site.baseurl }}/privacy-policy/)
- **Terms of Use** - See [Terms of Service]({{ site.baseurl }}/terms-of-service/)
- **Data Deletion** - Contact the developer via Discord

## Response Times

We aim to respond to:
- **Critical Issues** - Within 24-48 hours
- **General Questions** - Within 3-5 days
- **Feature Requests** - As time permits

Please be patient, as this is a community project maintained by volunteers.

---

**Need immediate help?** Check the [FAQ]({{ site.baseurl }}/faq/) first, then [open an issue](https://github.com/hugsndnugs/Event-Sentinel-bot-main/issues) on GitHub.

