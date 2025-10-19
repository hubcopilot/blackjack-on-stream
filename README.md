🎰 Twitch Blackjack Overlay

A browser-friendly Blackjack game built for OBS / streaming overlays, powered by Twitch chat commands.
This version includes queueing, turn-based and all-at-once modes, all-time earnings leaderboard, and auto round flow.

🚀 Features
🎮 Core Gameplay

Supports 1–10 seats at the table.

Each player starts with $100 bankroll.

Every round:

Bet: $10 deducted from each seated player.

Win: +$20 payout.

Push: +$10 refund.

Lose / Bust / Timeout: $0 return, bankroll reduced.

Dealer plays standard Blackjack rules:

Hits until ≥17, hits soft 17.

All players resolved after dealer reveals.

⏱️ Actions & Commands

Players interact entirely from chat:

!join — join the queue (valid for 30s; warning at 20s).

!leave — leave the queue before seated.

!hit — take another card.

!stand — end your turn.

Timeouts:

Turn-Based mode: 10s to act.

All-At-Once mode: 20s to act.

No action = auto elimination.

👥 Queue System

Shuffles new players from the queue into available seats.

Queue spots expire after 30s if not seated.

Players who bust/lose remain until round ends, then removed.

Queue resets each round (must re-join with !join).

🖥️ Display Layout

≤10 players: full-size cards and boxes.

>10 players: compact “mini cards” grid (fits ~50 players at 1920×1080).

Dealer panel always shown at top.

🕹️ Play Modes

Turn-Based (default): Players act one at a time (10s each).

All-At-Once: Everyone acts simultaneously (20s total).

Toggle with the “Mode” button in the overlay.

📊 Leaderboards

Bankrolls shown live next to each seated player.

All-Time Leaderboard (Top 5 earners) persists in browser storage.

Reset leaderboard any time with “Reset Leaderboard” button.

🎬 Round Flow

Manual override: Start Round button.

Auto-start: New round begins 4s after previous ends.

Flash summary overlay at end of round:

Dealer score.

Each player’s result (Win / Lose / Push / Timeout).

⚙️ Setup

Clone or download the project files.

Host the index.html on GitHub Pages or a static web server.

Add as a Browser Source in OBS:

URL: https://yourdomain.com/index.html?channel=YOUR_TWITCH_NAME

Size: 1920x1080

Connect via Twitch:

Enter your channel name at the top and click Connect.

📜 Chat Commands Summary
Command	Effect
!join	Queue into the game (valid 30s).
!leave	Leave the queue.
!hit	Take another card.
!stand	End your turn.
🖼️ OBS Tips

Recommended 1920×1080 browser source.

Overlay works best with dockable panels: Queue, Joins, Chat, Leaderboard.

Compact mode auto-activates for large games (11+ players).

🔧 Developer Notes

Written in HTML + JS (no backend) using tmi.js for Twitch chat.

Data persists locally with localStorage:

All-time earnings leaderboard.

Shoe built from 6 decks, reshuffled when empty.

📌 Changelog (Latest Update)

Added Turn-Based vs All-At-Once mode toggle.

Expanded max players from 4 → 10 (compact grid for >10).

Added 20s/30s queue expiry system.

Implemented bet logic:

$10 deducted at round start.

Win +$20, Push +$10, Lose $0.

Added flash summary overlay after each round.

Added Top 5 All-Time Leaderboard panel (resettable).

Implemented !leave command.

Queue resets after each round (players must re-join).

Optimized timers per mode (10s Turn-Based, 20s All-At-Once).

Improved results messaging (Dealer vs Player outcomes).
