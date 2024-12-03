# Telegram X-UI Monitor Bot

A Python-based Telegram bot that monitors your X-UI panel and sends periodic database status updates.

## Features

- 🔐 Secure credential management
- 🕒 Hourly database status updates
- 📊 Monitor X-UI panel status
- 🔄 Automatic reconnection
- 💾 Persistent storage of settings

## Requirements

- Python 3.7+
- Root access (for installation)
- Linux-based operating system
- Active Telegram Bot Token

## Installation

### Quick Install (Recommended)

```bash
curl -sSL https://raw.githubusercontent.com/yourusername/telegram-xui-bot/main/install.sh | sudo bash
```

### Manual Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/telegram-xui-bot.git
cd telegram-xui-bot
```

2. Install dependencies:
```bash
python3 -m pip install -r requirements.txt
```

3. Configure the bot:
   - Edit `src/config.py`
   - Replace `YOUR_BOT_TOKEN` with your Telegram Bot Token

4. Run the bot:
```bash
python3 src/bot.py
```

## Configuration

1. Get a Telegram Bot Token:
   - Message [@BotFather](https://t.me/BotFather) on Telegram
   - Create a new bot using `/newbot`
   - Copy the provided token

2. Configure the bot:
   - The token can be set during installation
   - Or manually in `src/config.py`

## Usage

1. Start the bot:
   - Send `/start` to your bot on Telegram
   - Follow the setup prompts

2. Available commands:
   - `/start` - Begin setup process
   - `/status` - Check monitoring status
   - `/cancel` - Cancel current operation

## Service Management

Monitor and control the bot service:

```bash
# Check service status
systemctl status telegram-xui-bot

# View real-time logs
journalctl -u telegram-xui-bot -f

# Restart the service
systemctl restart telegram-xui-bot

# Stop the service
systemctl stop telegram-xui-bot

# Start the service
systemctl start telegram-xui-bot
```

## Project Structure

```
telegram-xui-bot/
├── src/
│   ├── bot.py              # Main bot application
│   ├── config.py           # Configuration settings
│   ├── handlers/           # Command handlers
│   │   ├── auth_handler.py
│   │   ├── status_handler.py
│   │   └── conversation_states.py
│   ├── services/          # Business logic
│   │   └── update_service.py
│   └── storage/           # Data persistence
│       └── credentials.py
├── install.sh             # Installation script
├── requirements.txt       # Python dependencies
└── README.md             # Documentation
```

## Security Considerations

- Credentials are stored in `/opt/telegram-xui-bot/data/credentials.json`
- File permissions are set to 755 for the installation directory
- The service runs as root (required for system monitoring)
- Regular updates are recommended for security patches

## Troubleshooting

1. Bot not responding:
   ```bash
   # Check if service is running
   systemctl status telegram-xui-bot
   
   # View error logs
   journalctl -u telegram-xui-bot -e
   ```

2. Installation fails:
   - Ensure you have root access
   - Check system requirements
   - Verify internet connectivity

3. Authentication issues:
   - Confirm your bot token is correct
   - Ensure X-UI panel credentials are valid

## Contributing

1. Fork the repository
2. Create a feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Support

For support and questions:
- Open an issue on GitHub
- Contact the maintainer

## Acknowledgments

- [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot) for the Telegram Bot API wrapper
- The X-UI community for inspiration and feedback