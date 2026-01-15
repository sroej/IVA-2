# 🚀 IVAOTP - Telegram SMS Notification Bot

<div align="center">

[![Powered by AuroraInc](https://img.shields.io/badge/Powered%20by-AuroraInc-blueviolet?style=for-the-badge&logo=zap&logoColor=white)](https://aurorinc.com)
[![Developed by JadenAfrix](https://img.shields.io/badge/Developed%20by-JadenAfrix-blue?style=for-the-badge&logo=github&logoColor=white)](https://github.com/JadenAfrix)
[![GitHub stars](https://img.shields.io/github/stars/JadenAfrix/ivaotp?style=for-the-badge&logo=github)]([https://github.com/JadenAfrix/IVASMS-2](https://github.com/JadenAfrix1/IVASMS-2))

A powerful Telegram bot that receives SMS notifications, extracts OTP codes, and delivers them instantly to your Telegram chats with beautiful formatting and inline keyboard navigation.

![Bot Status](https://img.shields.io/badge/Status-Active-success?style=flat-square&logo=telegram&logoColor=white)
![Python Version](https://img.shields.io/badge/Python-3.8%2B-blue?style=flat-square&logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)
![Bot API](https://img.shields.io/badge/Bot%20API-20.4%2B-blue?style=flat-square)
![Platforms](https://img.shields.io/badge/Platforms-Linux%20%7C%20Mac%20%7C%20Windows%20%7C%20Render%20%7C%20Termux-blueviolet?style=flat-square)

</div>

---

## ✨ Features

- 📱 **Real-time SMS Monitoring** - Continuously checks for new SMS messages every 2 seconds
- 🔐 **Automatic OTP Extraction** - Intelligently extracts verification codes from messages
- 🌍 **Country Detection** - Identifies sender country with flag emojis (200+ countries)
- 🏢 **Service Recognition** - Identifies 150+ services (Google, Facebook, WhatsApp, Twitter, etc.)
- 📊 **Multiple Chat Support** - Send messages to multiple Telegram chats simultaneously
- 🎮 **Inline Keyboard Navigation** - Easy access buttons for quick actions (customizable)
- ⚡ **Admin Control** - Manage chat IDs and bot settings via Telegram commands
- 💾 **State Persistence** - Remembers processed SMS to avoid duplicates
- 🎨 **Beautiful Formatting** - Rich message formatting with emojis and markdown
- 📈 **Production Ready** - Error handling, logging, and security best practices

---

## 📋 Prerequisites

Before you begin, ensure you have the following:

- **Python** 3.8 or higher
- **pip** (Python package manager)
- A **Telegram Bot Token** (get it from [@BotFather](https://t.me/BotFather))
- **Active Telegram Account**
- **IVASMS Account** (for SMS API access)
- Internet connection

---

## 🛠️ Installation

### Option 1: Traditional Installation (Linux/Mac/Windows)

1. **Clone or Download the Repository**
   ```bash
   git clone https://github.com/JadenAfrix/ivaotp.git
   cd ivaotp
   ```

2. **Create a Virtual Environment** (Recommended)
   ```bash
   python -m venv venv
   
   # On Linux/Mac:
   source venv/bin/activate
   
   # On Windows:
   venv\Scripts\activate
   ```

3. **Install Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Configure the Bot**
   - Open `main.py` with your favorite text editor
   - Replace `YOUR_BOT_TOKEN` with your Telegram Bot Token from [@BotFather](https://t.me/BotFather)
   - Update `USERNAME` and `PASSWORD` with your IVASMS account credentials
   - Update `ADMIN_CHAT_IDS` with your Telegram User ID
   - Update button URLs in the `INLINE_BUTTONS` section as needed

5. **Run the Bot**
   ```bash
   python main.py
   ```

You should see:
```
🚀 iVasms to Telegram Bot is starting...
✅ SMS checking active: polling every 2 seconds.
🤖 Bot is now online. Ready to listen for commands.
```

---

### Option 2: Termux Installation (Android)

Run the bot directly on your Android device!

1. **Install Termux** (from [F-Droid](https://f-droid.org/packages/com.termux/) or Google Play Store)

2. **Update and Upgrade Termux**
   ```bash
   pkg update && pkg upgrade
   ```

3. **Install Python and Git**
   ```bash
   pkg install python git
   ```

4. **Clone the Repository**
   ```bash
   git clone https://github.com/JadenAfrix/ivaotp.git
   cd ivaotp
   ```

5. **Install Python Dependencies**
   ```bash
   pip install -r requirements.txt
   ```

6. **Configure the Bot**
   ```bash
   nano main.py
   ```
   - Edit the configuration section with your credentials
   - Press `Ctrl+X`, then `Y`, then `Enter` to save and exit

7. **Run the Bot**
   ```bash
   python main.py
   ```

**Tip - Keep Bot Running in Background:**
```bash
nohup python main.py > bot.log &
```

To view logs:
```bash
tail -f bot.log
```

To stop the bot:
```bash
pkill -f "python main.py"
```

---

### Option 3: Deploy on Render.com (Cloud Hosting - Recommended)

Deploy your bot to Render for always-on performance!

#### Prerequisites:
- GitHub account with your bot code pushed
- Free [Render.com](https://render.com) account

#### Step-by-Step Deployment:

1. **Push Your Code to GitHub**
   ```bash
   git init
   git add .
   git commit -m "Initial IVAOTP bot commit"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/ivaotp.git
   git push -u origin main
   ```

2. **Sign Up on Render.com**
   - Visit [render.com](https://render.com)
   - Sign up with GitHub (recommended for easier auth)

3. **Create a New Web Service**
   - Click "New +" → "Web Service"
   - Select "Connect a repository"
   - Find and connect your `ivaotp` repository
   - Click "Connect"

4. **Configure the Service**
   - **Name:** `ivaotp-bot`
   - **Environment:** `Python 3`
   - **Build Command:** `pip install -r requirements.txt`
   - **Start Command:** `python main.py`
   - **Plan:** Free tier (perfect for this bot)

5. **Add Environment Variables**
   - Scroll to "Environment"
   - Click "Add Environment Variable"
   - Add each variable:
     ```
     YOUR_BOT_TOKEN=your_bot_token_from_BotFather
     USERNAME=your_ivasms_email@example.com
     PASSWORD=your_ivasms_password
     ADMIN_CHAT_IDS=123456789
     ```

6. **Deploy**
   - Click "Create Web Service"
   - Wait for the build to complete (2-3 minutes)
   - You'll get a URL: `https://ivaotp-xxxx.onrender.com`
   - Your bot is now live 24/7!

**Note:** Free tier services may go to sleep after 15 minutes of inactivity. For continuous uptime, upgrade to a paid plan or use a keep-alive service.

---

## ⚙️ Configuration Guide

### Main Settings in `main.py`

```python
# Your Telegram Bot Token (get from @BotFather)
YOUR_BOT_TOKEN = "8216244005:AAHd2xupqCn6Saz9Igpugu-kU4khkPC3WV4"

# Admin User IDs (only these users can manage the bot)
ADMIN_CHAT_IDS = ["7500869913", "YOUR_OTHER_ADMIN_ID"]

# IVASMS Login Credentials
USERNAME = "tawandamahachi07@gmail.com"
PASSWORD = "mahachi2007"

# How often to check for new SMS (in seconds)
POLLING_INTERVAL_SECONDS = 2  # Check every 2 seconds
```

### Getting Your Telegram User ID

1. Start the bot: `/start`
2. Check your terminal output - it will show your User ID
3. Add this ID to `ADMIN_CHAT_IDS`

### Customize Inline Buttons

Edit the `INLINE_BUTTONS` section to add your links:

```python
INLINE_BUTTONS = [
    InlineKeyboardButton("📱 NUMBER CHANNEL", url="https://t.me/mrafrixtech"),
    InlineKeyboardButton("BACKUP CHANNEL", url="https://t.me/auroratechinc"),
    InlineKeyboardButton("OTP GROUP", url="https://t.me/afrixotpgc"),
    InlineKeyboardButton("CONTACT DEV", url="https://t.me/jaden_afrix"),
]
```

Each button appears on its own row. Update the URLs anytime without restarting!

---

## 📱 Bot Commands

Use these commands in Telegram to control your bot:

| Command | Description | Who Can Use | Example |
|---------|-------------|------------|---------|
| `/start` | Initialize bot and see inline buttons | Everyone | `/start` |
| `/add_chat <chat_id>` | Add a chat to receive notifications | Admin Only | `/add_chat -1001234567890` |
| `/remove_chat <chat_id>` | Remove a chat from notifications | Admin Only | `/remove_chat -1001234567890` |
| `/list_chats` | View all registered chat IDs | Admin Only | `/list_chats` |

### How to Get Chat ID:

For **Personal Chat:**
- Start the bot and check the terminal output

For **Group/Channel:**
- Add bot to the group as admin
- Send `/list_chats` to the group
- The group ID will be displayed

---

## 🔧 Troubleshooting

### Bot Not Receiving Messages?
**Solution:**
1. Verify your Bot Token from [@BotFather](https://t.me/BotFather)
2. Check IVASMS login credentials are correct
3. Ensure your firewall allows outgoing connections
4. Check the console for error messages
5. Make sure Python version is 3.8+

### "Login Failed" Error
**Solution:**
- Your IVASMS credentials might be incorrect
- IVASMS website might be temporarily down
- Check your internet connection
- Try logging in manually on the IVASMS website

### Can't Get Bot Token?
**Solution:**
1. Go to [@BotFather](https://t.me/BotFather) on Telegram
2. Send `/newbot`
3. Follow the prompts to create your bot
4. Copy the token and paste it in `main.py`

### "JobQueue" Error on Startup?
**Solution:**
```bash
pip install "python-telegram-bot[job-queue]"
```

### Bot Goes Offline on Render?
**Solution:**
- Free tier goes to sleep after 15 minutes of inactivity
- Upgrade to a paid plan for 24/7 uptime
- Or use a keep-alive service like Uptimerobot

### Memory or Timeout Errors?
**Solution:**
1. Reduce `POLLING_INTERVAL_SECONDS` if too frequent
2. Check if too many chats are registered
3. Clear old data from `processed_sms_ids.json`

---

## 📊 File Structure

```
ivaotp/
├── main.py                      # Main bot application
├── requirements.txt             # Python dependencies
├── processed_sms_ids.json       # Stores processed SMS IDs (auto-generated)
├── chat_ids.json                # Stores chat IDs (auto-generated)
├── README.md                    # Documentation
└── .gitignore                   # Git ignore file (recommended)
```

### Recommended `.gitignore`:
```
venv/
__pycache__/
*.pyc
.env
processed_sms_ids.json
chat_ids.json
*.log
```

---

## 🔐 Security Best Practices

⚠️ **Important Security Measures:**

1. **Never Commit Credentials to GitHub**
   ```bash
   # Use environment variables on Render instead
   # Add .env to .gitignore
   echo ".env" >> .gitignore
   ```

2. **Use Strong Passwords**
   - Your IVASMS password is stored locally
   - Create a dedicated IVASMS account for this bot
   - Change password regularly

3. **Limit Admin Access**
   - Only add trusted user IDs to `ADMIN_CHAT_IDS`
   - Admins can manage all bot settings
   - Remove users when they no longer need access

4. **Regular Backups**
   ```bash
   # Backup important data
   cp chat_ids.json chat_ids.json.backup
   cp processed_sms_ids.json processed_sms_ids.json.backup
   ```

5. **Monitor Bot Activity**
   - Check console logs regularly
   - Review error messages for suspicious activity
   - Monitor which chats are registered

---

## 📞 Support & Contact

- **Bug Reports:** Open an issue on [GitHub](https://github.com/JadenAfrix/ivaotp/issues)
- **Feature Requests:** Create a discussion on GitHub
- **Direct Contact:** [@jaden_afrix](https://t.me/jaden_afrix) on Telegram
- **Questions?** Check the troubleshooting section above

---

## 🎨 Credits & Attribution

<div align="center">

### ⚡ Powered by **AuroraInc**
*Premium Technology Solutions*

### 🚀 Developed by **JadenAfrix**  
*Full-Stack Developer & Bot Creator*

[![AuroraInc](https://img.shields.io/badge/🔗_AuroraInc-Premium%20Technology-blueviolet?style=for-the-badge)](https://aurorinc.com)
[![JadenAfrix GitHub](https://img.shields.io/badge/🔗_JadenAfrix-GitHub-black?style=for-the-badge&logo=github)](https://github.com/JadenAfrix)

</div>

---

## 📜 License

This project is licensed under the **MIT License** - see the LICENSE file for details.

You are free to use, modify, and distribute this project for personal or commercial purposes.

---

## 🙏 Acknowledgments

- [python-telegram-bot](https://github.com/python-telegram-bot/python-telegram-bot) - Amazing library
- [IVASMS](https://www.ivasms.com/) - SMS API provider
- [Render.com](https://render.com) - Free hosting platform
- [Termux](https://termux.com/) - Android terminal emulator
- Community contributors and testers

---

## 📈 Status & Activity

![Activity](https://img.shields.io/badge/Activity-Active%20Development-brightgreen?style=flat-square)
![Last Updated](https://img.shields.io/badge/Last%20Updated-2026-blue?style=flat-square)
![Maintained](https://img.shields.io/badge/Maintained%3F-Yes-success?style=flat-square)

---

<div align="center">

**Made with ❤️ by the AuroraInc Development Team**

⭐ **If you found this useful, please star the repository!** ⭐

</div>
