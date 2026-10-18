# Hollow-purple-eSports-bot

eSports Discord + GitHub automation — pura setup is repo me hai.

## Kya hai isme?
1. **`.github/workflows/discord-notify.yml`** → GitHub pe push / PR / issue / release / daily cron hote hi Discord channel me embed jayega (webhook se)
2. **`bot/`** → Auto-DM bot jo naye member ko DM karta hai + Verify button par role deta hai + `POST /github` se GitHub events ko channel me forward karta hai
3. **`setup.sh`** → Ek command me GitHub secret set + workflow push + test run

Live verify: Discord webhook `1561388086745899058` same channel `1560004874580533338` pe test message **HTTP 200** deliver hua hai (18 Oct 2026).

> ⚠️ Webhook URL / Bot Token ko kabhi file me commit mat karna — `.env` use karo, `.gitignore` me block hai.

## Quick Start — GitHub → Discord webhook
```bash
# 1. PAT banao: github.com/settings/tokens?type=beta
#    Contents: R/W, Actions: R/W, Workflows: R/W
export GITHUB_TOKEN=github_pat_xxx
export DISCORD_WEBHOOK='https://discord.com/api/webhooks/ID/TOKEN'
./setup.sh glverma592-cmd/Hollow-purple-eSports-bot
```

## Bot chalana (Auto-DM)
```bash
cd bot
cp .env.example .env   # andar DISCORD_BOT_TOKEN, VERIFY_ROLE_ID, WELCOME_CHANNEL_ID bharo
pip install -r requirements.txt
python bot.py
# test bina login ke:
python test_bot.py   # 7/7 OK
```

Repo: https://github.com/glverma592-cmd/Hollow-purple-eSports-bot

## Hosting (BotKeep / Render)
- Repository: `glverma592-cmd/Hollow-purple-eSports-bot`, Branch: `main`
- Install: `pip install -r requirements.txt`
- Start: `python main.py`
- Env: `DISCORD_BOT_TOKEN`, `WELCOME_CHANNEL_ID=1559886513423257610`, `VERIFY_ROLE_ID=0`, `REQUIRE_VERIFY=0`
