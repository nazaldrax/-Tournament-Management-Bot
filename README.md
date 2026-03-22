# 🎮 Tournament Management Bot

## Complete Documentation & Setup Guide
// ============================================
// 🔧 Project Information
// --------------------------------------------
// Made by: Drax
// Discord: .kingdrax
// Version: v1 (2026)
//
// This project is open-source and free to use.
// You are allowed to use, modify, and share it.
//
// ❌ Selling this code is strictly not allowed.
// ❌ Do not claim this code as your own.
//
// Credit must be given to the original author.
//
// © 2026 Drax
// ============================================


---

## 📖 Table of Contents
- [Bot Overview](#-bot-overview)
- [Features](#-features)
- [Installation](#-installation)
- [Configuration](#-configuration)
- [Command List](#-command-list)
- [Quick Start Guide](#-quick-start-guide)
- [Special Features](#-special-features)
- [Data Structure](#-data-structure)
- [Permissions](#-permissions)
- [Troubleshooting](#-troubleshooting)
- [Support](#-support)

---

## 🤖 Bot Overview

**Tournament Management Bot** is a comprehensive Discord bot designed to streamline tournament organization, team management, and match coordination. It handles everything from team creation to points tracking, payment management, and voice channel control - all in one place.

### Key Capabilities:
- ✅ Team creation with automated channels and roles
- ✅ Player management with nickname sync
- ✅ Points system with kill/takedown/survival tracking
- ✅ Payment tracking with proof uploads
- ✅ Voice channel control (mute/unmute/disconnect)
- ✅ Automated statistics display (roster, points table, skins)
- ✅ Database backup system
- ✅ Tournament bracket organization (groups & rounds)
- ✅ Comprehensive logging system

---

## ✨ Features

### 🏆 **Tournament Management**
- Create teams with dedicated text/voice channels
- Assign teams to groups and rounds
- Team role with separate member display and mentionable permissions
- Team renaming with automatic channel updates

### 👥 **Team Member Management**
- Add/remove players with nickname synchronization
- Transfer players between teams
- Captain assignment with special role
- Player history tracking

### 🎨 **Skin System**
- Unique skin assignment per team
- Skin availability checking
- Organized display by group and round
- Automatic skin info updates

### 🏅 **Point System**
- Point awards: Kills (+1), Takedowns (+1), Survival (+1)
- Point history tracking
- Organized points table by round/group
- Points reset functionality

### 💰 **Payment System**
- Payment status tracking
- Proof image upload support
- Payment history with notes
- Payment statistics dashboard

### 🎤 **Voice Channel Management**
- Individual player mute/unmute
- Team-wide mute/unmute
- Global mute/unmute all players
- Global disconnect all players
- Voice call system with clickable links

### 📊 **Auto-Updating Displays**
- **Team Roster** - Shows all teams with member counts
- **Points Table** - Live standings by round and group
- **Skin Info** - Organized by tournament structure
- **Bot Status** - Real-time team count in bot status

### 🔐 **Security & Logging**
- Admin-only commands with role-based access
- Captain-only team management panel
- Command usage logging
- Database change tracking
- Player activity channel

---

## 🚀 Installation

### Prerequisites
- Node.js v16.9.0 or higher
- Discord Bot Token ([Create one here](https://discord.com/developers/applications))
- A Discord server with admin permissions

### Step 1: Clone & Install
```bash
# Clone the repository
git clone https://github.com/yourusername/tournament-bot.git
cd tournament-bot

# Install dependencies
npm install discord.js
```

### Step 2: Configure the Bot

Create `config.json` in the root directory:
```json
{
  "token": "YOUR_MAIN_BOT_TOKEN_HERE",
  "dbBotToken": "YOUR_DATABASE_BOT_TOKEN_HERE",
  "clientId": "YOUR_MAIN_BOT_CLIENT_ID_HERE",
  "dbClientId": "YOUR_DATABASE_BOT_CLIENT_ID_HERE",
  "adminRoleIds": ["ADMIN_ROLE_ID_1", "ADMIN_ROLE_ID_2"],
  "captainRoleIds": ["CAPTAIN_ROLE_ID"],
  "groupNames": ["Group A", "Group B", "Group C", "Group D"],
  "roundNames": ["Round 1", "Round 2", "Round 3", "Quarter Finals", "Semi Finals", "Finals"],
  "announcementChannel": "ANNOUNCEMENT_CHANNEL_ID",
  "rosterChannel": "ROSTER_CHANNEL_ID",
  "pointsTableChannel": "POINTS_TABLE_CHANNEL_ID",
  "skinInfoChannel": "SKIN_INFO_CHANNEL_ID",
  "paymentChannel": "PAYMENT_CHANNEL_ID",
  "playerChannel": "PLAYER_LOG_CHANNEL_ID",
  "logChannel": "COMMAND_LOG_CHANNEL_ID",
  "guildId": "YOUR_SERVER_ID",
  "dbGuildId": "DATABASE_BACKUP_SERVER_ID",
  "dbChannelId": "DATABASE_BACKUP_CHANNEL_ID",
  "streamUrl": "https://www.twitch.tv/yourchannel"
}
```

### Step 3: Create Required Channels

Create these channels in your Discord server:
- `#announcements` - Tournament announcements
- `#roster` - Team roster display
- `#points-table` - Points leaderboard
- `#skin-info` - Team skins display
- `#payment-logs` - Payment tracking
- `#player-logs` - Player activity logs
- `#command-logs` - Bot command logs
- `#team-management` - Team management panel channel (ID: 1478324402876710973)

### Step 4: Set Up Bot Permissions

Invite the bot with these permissions:
- `Administrator` (or these specific permissions):
  - Manage Roles
  - Manage Channels
  - Send Messages
  - Embed Links
  - Attach Files
  - Read Message History
  - Connect (Voice)
  - Speak (Voice)
  - Mute Members
  - Move Members

### Step 5: Start the Bot
```bash
node index.js
```

---

## ⚙️ Configuration

### Required IDs
| Field | Description |
|-------|-------------|
| `token` | Your main Discord bot token |
| `dbBotToken` | Database backup bot token |
| `clientId` | Main bot application ID |
| `dbClientId` | Database bot application ID |
| `adminRoleIds` | Array of role IDs with admin access |
| `captainRoleIds` | Array of role IDs for team captains |
| `guildId` | Your Discord server ID |
| `dbGuildId` | Server ID for database backups |
| `dbChannelId` | Channel ID for database backups |

### Optional Configuration
| Field | Description | Default |
|-------|-------------|---------|
| `groupNames` | Tournament group names | Group A-D |
| `roundNames` | Tournament round names | Round 1-3, Quarter, Semi, Finals |
| `streamUrl` | Twitch/stream URL for status | https://www.twitch.tv/tournament |

---

## 📋 Command List

### 🏠 General Commands
| Command | Description | Example |
|---------|-------------|---------|
| `/help` | Show all commands | `/help` or `/help team` |
| `/stats` | View team/player stats | `/stats team Warriors` |
| `/skininfo` | View all team skins | `/skininfo` |
| `/pointsinfo` | View team points | `/pointsinfo Warriors` |
| `/payinfo` | View payment status | `/payinfo` |
| `/teaminfo` | View team details | `/teaminfo Warriors` |
| `/checkskin` | Check skin availability | `/checkskin skin:"Dragon"` |

### 👥 Team Management
| Command | Description | Example |
|---------|-------------|---------|
| `/createteam` | Create new team | `/createteam name:Warriors captain:@User` |
| `/deleteteam` | Delete team | `/deleteteam team:Warriors confirm:CONFIRM` |
| `/renameteam` | Rename team | `/renameteam team:Warriors new_name:Gladiators` |
| `/setteam` | Add player to team | `/setteam user:@Player team:Warriors nickname:"King"` |
| `/removeteam` | Remove player from team | `/removeteam user:@Player reason:"Inactive"` |
| `/captain` | Set team captain | `/captain user:@User team:Warriors nickname:"Leader"` |
| `/playertransfer` | Transfer player | `/playertransfer user:@Player old_team:Warriors new_team:Titans` |
| `/teammanage` | Open team management panel | `/teammanage` (Captain only) |

### 🎨 Skin System
| Command | Description | Example |
|---------|-------------|---------|
| `/setskin` | Set team skin | `/setskin team:Warriors skin:"Dragon Warrior"` |
| `/checkskin` | Check skin availability | `/checkskin skin:"Phoenix"` |
| `/setgroup` | Assign team to group/round | `/setgroup team:Warriors group:"Group A" round:"Round 1"` |

### 🏆 Point System
| Command | Description | Example |
|---------|-------------|---------|
| `/setpoint` | Add points to team | `/setpoint team:Warriors option:kill amount:5` |
| `/resetpoints` | Reset all points | `/resetpoints confirm:CONFIRM` |
| `/pointsinfo` | View points | `/pointsinfo Warriors` |

### 💰 Payment System
| Command | Description | Example |
|---------|-------------|---------|
| `/payment` | Update payment status | `/payment team:Warriors status:true note:"Paid"` |
| `/paystats` | View payment stats | `/paystats Warriors` |

### 🎤 Voice Commands
| Command | Description | Example |
|---------|-------------|---------|
| `/callvc` | Call player to VC | `/callvc user:@Player message:"Join!"` |
| `/mute` | Mute players | `/mute player user:@Player action:mute` |
| `/muteall` | Mute all players | `/muteall reason:"Tournament start"` |
| `/unmuteall` | Unmute all players | `/unmuteall reason:"Match end"` |
| `/disconnectall` | Disconnect all players | `/disconnectall reason:"Maintenance"` |

### ⚙️ Admin Commands
| Command | Description | Example |
|---------|-------------|---------|
| `/disqualified` | Disqualify team | `/disqualified team:Warriors reason:"Rule violation"` |
| `/chagename` | Change player nickname | `/chagename user:@Player nickname:"NewName"` |
| `/setvcstats` | Control voice stats | `/setvcstats setchannel #voice-stats` |
| `?sendteam` | Message all teams | `?sendteam "Practice at 5PM"` |

---

## 🚀 Quick Start Guide

### Step 1: Create Your First Team
```
/createteam name:Warriors captain:@Captain1
```

### Step 2: Add Players
```
/setteam user:@Player1 team:Warriors nickname:"WarriorKing"
```

### Step 3: Assign to Group & Round
```
/setgroup team:Warriors group:"Group A" round:"Round 1"
```

### Step 4: Award Points
```
/setpoint team:Warriors option:kill amount:5 reason:"Match victory"
```

### Step 5: Record Payment
```
/payment team:Warriors status:true note:"Paid via PayPal"
```

### Step 6: View Progress
```
/teaminfo team:Warriors     # Team details
/pointsinfo                  # All points
/skininfo                    # All skins
/paystats                    # Payment status
```

---

## 🎖️ Special Features

### 📋 Team Management Panel
Captain-only interactive panel accessible via `/teammanage`:
- **Join** - Add members with nickname
- **Kick** - Remove members with reason
- **Update** - Change member nicknames
- **List** - View all team members

### 💬 Automatic Message System
Send formatted messages in the team management channel:
```
TEAM MENTION :@TeamRole
JOIN/KICK : join
MEMBER :PlayerName | Nickname
MENTION :@User
```
The bot processes automatically and sends confirmation via DM.

### 📊 Live Statistics
| Display | Update Frequency | Content |
|---------|-----------------|---------|
| Team Roster | Every change | All teams with members |
| Points Table | Every change | Organized by round/group |
| Skin Info | Every change | Teams and their skins |
| Bot Status | Every 5 minutes | Team count (X/48) |

### 💾 Database Backup
- Automatic backups every 5 minutes
- Timestamped JSON files
- Separate database bot for redundancy
- Final backup on shutdown

---

## 📁 Data Structure

### team.json Structure
```json
{
  "TeamName": {
    "name": "TeamName",
    "roleId": "123456789",
    "roleHoist": true,
    "roleMentionable": true,
    "categoryId": "123456789",
    "textChannelId": "123456789",
    "voiceChannelId": "123456789",
    "captainId": "123456789",
    "captainTag": "User#1234",
    "skin": "Dragon",
    "group": "Group A",
    "round": "Round 1",
    "points": {
      "kill": 25,
      "takedown": 12,
      "survival": 8,
      "total": 45,
      "history": []
    },
    "payment": {
      "status": true,
      "lastUpdated": "2024-01-01T00:00:00.000Z",
      "lastUpdatedBy": "123456789",
      "proofs": []
    },
    "players": {},
    "createdAt": "2024-01-01T00:00:00.000Z",
    "disqualified": null
  }
}
```

---

## 🔒 Permissions

### Required Bot Permissions
| Permission | Purpose |
|------------|---------|
| Manage Roles | Assign team roles |
| Manage Channels | Create/rename team channels |
| Send Messages | Bot responses and announcements |
| Embed Links | Rich embeds for information |
| Attach Files | Payment proof uploads |
| Read Message History | Edit existing messages |
| Connect | Join voice channels |
| Speak | Voice channel stats |
| Mute Members | Voice channel muting |
| Move Members | Voice channel disconnection |

### Role Requirements
- **Admin Role**: Full command access
- **Captain Role**: Team management access
- **Team Role**: Channel access for team members

---

## 🛠️ Troubleshooting

### Common Issues & Solutions

**Bot won't join voice channel**
- Check bot has "Connect" permission
- Verify voice channel ID is correct in config
- Ensure bot has permission to view the channel

**Commands not appearing in menu**
- Wait up to 1 hour for global commands
- Use guild-specific commands for instant updates
- Restart bot to refresh registration

**Role not assigned to new member**
- Check bot role hierarchy (bot role must be above team roles)
- Verify bot has "Manage Roles" permission
- Check for role assignment errors in console logs

**Channel permissions not syncing**
- Use `/setteam` with `sync_permissions:true`
- Check bot has "Manage Channels" permission
- Verify role permissions are set correctly

**Database backup not sending**
- Verify database bot token is correct
- Check channel permissions for database bot
- Ensure `dbGuildId` and `dbChannelId` are correct

### Console Errors
- `DiscordAPIError[10062]: Unknown interaction` - Interaction timed out, defer reply earlier
- `DiscordAPIError[50001]: Missing Access` - Bot lacks required permissions
- `MODULE_NOT_FOUND` - Missing dependency, run `npm install`

---

## 📞 Support

### Need Help?
- Use `/help` for command reference
- Check the announcement channel for updates
- Contact tournament administrators
- Review console logs for errors

### Useful Links
- [Discord.js Documentation](https://discord.js.org/)
- [Discord Developer Portal](https://discord.com/developers/applications)
- [Node.js Documentation](https://nodejs.org/)

---

## 📝 License

This bot is provided for tournament management purposes. Modify and adapt as needed for your community.

---

## 🎉 Credits

Developed for seamless tournament organization and management.

---

**✨ Your tournament is now fully automated! Enjoy smooth operations and fair play! 🏆**
