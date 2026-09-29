# Voicecord Control Center

A polished web dashboard for managing Discord client presence, rich activity, and voice-channel sessions.

This project preserves the original Voicecord token workflow: saved accounts remain in tokens.json, and the dashboard still supports token add/edit/delete, presence, RPC, voice join/disconnect, and bulk operations.

## Included

- Responsive command-center dashboard with account health, activity, and live voice views
- Token management with masked display and the original raw-token storage contract
- Online, idle, DND, and invisible presence controls
- Custom status and rich presence with assets, timestamps, streaming URLs, and buttons
- Voice auto-join plus per-token and bulk disconnect controls
- Command palette (Ctrl/Cmd + K) for fast operations
- Profile refresh, restart controls, activity log, and mobile-friendly layout
- Railway-ready Procfile and railway.toml

## Run locally

    python -m venv .venv
    source .venv/bin/activate
    pip install -r requirements.txt
    export ADMIN_USER=admin
    export ADMIN_PASS=change-this-password
    python run.py

Open http://localhost:8000 and sign in with the configured admin credentials.

## Deploy

Set these environment variables in your host:

- ADMIN_USER
- ADMIN_PASS
- PORT (provided automatically by most hosts)

The filesystem must be persistent if you want tokens.json to survive redeploys. Never commit config.json, tokens.json, or real Discord tokens.

## Project layout

- backend/main.py — FastAPI pages, authentication, token APIs, voice APIs, bulk commands, and activity
- backend/bot.py — gateway client and presence/voice payload handling
- frontend/index.html — dashboard structure
- frontend/app.js — dashboard state and commands
- frontend/style.css — responsive visual system
- config.example.json — safe local configuration example

## Important

User-token automation can violate Discord's Terms of Service. Use this project only where you have permission and accept the platform risk.
