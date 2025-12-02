# Discord Bot Scripts

**Last Updated**: 2025-11-20
**Cleanup Action**: ULTRATHINK Directory Cleanup

---

## 📁 Directory Structure

```
discord_bot/scripts/
├── management/  - Bot management and diagnostic scripts
└── utils/       - Utility scripts
```

---

## 🛠️ management/ - Bot Management Scripts

### Shell Scripts

#### **start_bot.sh** (1.2K)
Start Discord Bot
```bash
./discord_bot/scripts/management/start_bot.sh
```

#### **stop_bot.sh** (897B)
Stop Discord Bot
```bash
./discord_bot/scripts/management/stop_bot.sh
```

#### **check_bot_instances.sh** (1.4K)
Check running Bot instances
```bash
./discord_bot/scripts/management/check_bot_instances.sh
```

#### **verify_fix.sh** (4.6K)
Verify Bot fixes
```bash
./discord_bot/scripts/management/verify_fix.sh
```

---

### Node.js Scripts

#### **check_command_id.js** (899B)
Check command ID
```bash
node discord_bot/scripts/management/check_command_id.js
```

#### **clear-global-commands.js** (504B)
Clear global commands
```bash
node discord_bot/scripts/management/clear-global-commands.js
```

#### **debug-interaction.js** (8.0K)
Debug interaction issues
```bash
node discord_bot/scripts/management/debug-interaction.js
```

#### **get-command-ids.js** (1.7K)
Get all command IDs
```bash
node discord_bot/scripts/management/get-command-ids.js
```

#### **reset-commands.js** (5.0K)
Reset Discord commands
```bash
node discord_bot/scripts/management/reset-commands.js
```

#### **verify-commands.js** (4.1K)
Verify command registration status
```bash
node discord_bot/scripts/management/verify-commands.js
```

---

## 🎯 Common Commands

### Start/Stop Bot
```bash
# Start
./discord_bot/scripts/management/start_bot.sh

# Stop
./discord_bot/scripts/management/stop_bot.sh

# Check Instances
./discord_bot/scripts/management/check_bot_instances.sh
```

### Command Management
```bash
# Deploy Commands (from root directory)
node discord_bot/deploy-commands.js

# Verify Commands
node discord_bot/scripts/management/verify-commands.js

# Reset Commands
node discord_bot/scripts/management/reset-commands.js
```

### Debugging
```bash
# Debug Interaction Issues
node discord_bot/scripts/management/debug-interaction.js

# Check Command ID
node discord_bot/scripts/management/check_command_id.js
```

---

**Cleanup Completed**: 2025-11-20
