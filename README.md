# Telegram Promotion Rotation Bot

A Telegram bot that automatically posts promotional messages to approved Telegram groups every 5 minutes.

Each promotion contains:

- GIF/animation
- Caption
- One clickable URL button

The bot rotates:

Promo 1 → Promo 2 → Promo 3 → Promo 1 → ...

## Important Behavior

This is NOT an AI chatbot.

The bot does not reply to normal messages.

It only responds to supported commands.

For example:

User:
Hello

Bot:
No response.

User:
/promo_status

Bot:
Returns the promotion status.

---

## Group-Only Promotion

Scheduled promotions are ONLY sent to Telegram groups/supergroups where the bot is authorized.

The bot NEVER sends scheduled promotions to:

- Private DMs
- Admin DMs
- Individual users
- Private conversations
- Unauthorized groups

The administrator's private DM is only used as the control panel.

If the bot is added to an unauthorized group, it should leave that group.

---

# Features

## Promotion Rotation

Every 5 minutes:

1. Send Promo 1
2. Send Promo 2
3. Send Promo 3
4. Return to Promo 1
5. Repeat forever

Only one promotion is sent per scheduled run.

The bot never combines all promotions into one message.

---

# Promotion Format

Every promotion contains exactly:

- One GIF/animation
- One caption
- One URL button

Example:

[ GIF ]

💕 Join our backup group!

Stay connected with us and don't miss our updates.

[ 🔗 JOIN BACKUP ]

---

# Admin Commands

Only the configured administrator can use these commands.

### Configure Promo 1

/setpromo1

The bot asks for:

1. GIF/animation
2. Caption
3. Button text
4. Button URL

Then:

✅ Promo 1 saved.

### Configure Promo 2

/setpromo2

The bot asks for:

1. GIF/animation
2. Caption
3. Button text
4. Button URL

Then:

✅ Promo 2 saved.

### Configure Promo 3

/setpromo3

The bot asks for:

1. GIF/animation
2. Caption
3. Button text
4. Button URL

Then:

✅ Promo 3 saved.

---

# Preview Commands

/preview1

Shows Promo 1 privately to the administrator.

/preview2

Shows Promo 2 privately to the administrator.

/preview3

Shows Promo 3 privately to the administrator.

Preview messages must NOT be sent to the group.

---

# Status

/promo_status

Shows:

- Promo 1 configured or not
- Promo 2 configured or not
- Promo 3 configured or not
- Current rotation position
- Approved groups

---

# Cancel

/cancel

Cancels the current promotion setup without deleting the previously saved promotion.

---

# Normal Messages

The bot must NOT behave like an AI assistant.

Examples of messages that must be ignored:

hello

hi

how are you?

test

what's up?

send promotion

good morning

The bot should remain completely silent.

Only valid commands or scheduled promotion actions should cause a response.

---

# No Typing Animation

The bot must not show:

- typing...
- upload animation
- AI thinking animation
- typing indicators

Commands should respond normally without pretending to type.

---

# Data Structure

Each promotion should contain:

```text
promoId
position
animation
caption
buttonText
buttonUrl
active
updatedAt
