# Twitch Blackjack Overlay 🎲🃏

A **browser-source Blackjack game** for Twitch streams.  
- 4 players play each round.  
- Players join the table via chat commands.  
- The game runs automatically round by round, no manual dealing.  
- Built for OBS / GitHub Pages, no server backend needed.  

---

## 🌟 Features
- **4 players per table** (chosen randomly if more than 4 join).
- **Queue system**: Extra players wait their turn. When someone busts, the next in queue joins.
- **Fixed $10 bets**: Everyone starts with $10. Wins add money, but the bet size never changes.
- **Player actions**:  
  - `!join` → join the queue.  
  - `!hit` → draw another card.  
  - `!stand` → hold your hand.  
- **20-second countdown timer** per turn.  
  - If a player doesn’t act in time, they **bust automatically**.  
- **Dealer rules**: Hits until 17+, stands on soft 17.  
- **Auto-rounds**: After dealer finishes, results show → 5s delay → next round starts.  
- **OBS ready**: Load as a **browser source** in OBS.  

---

## 🖥️ How to Use
1. **Clone or download** this repo.
2. Open `index.html` in a browser to test locally.  
3. For streaming:  
   - Upload to **GitHub Pages** (Settings → Pages → Source → `main` branch).  
   - Access the game at `https://yourname.github.io/blackjack/`.  
   - In OBS, add a **Browser Source** with that URL.  
   - Add `?channel=YOURTWITCHNAME` at the end of the URL.  
     Example:  
     ```
     https://yourname.github.io/blackjack/?channel=ryaah
     ```

---

## 🕹️ Commands (for chat)
- `!join` → join the game (enters queue).  
- `!hit` → draw another card (only works on your turn).  
- `!stand` → hold your hand (only works on your turn).  

---

## 🔄 Game Flow
1. Streamer connects overlay with `?channel=...`.  
2. Viewers type `!join` to enter queue.  
3. 4 players are picked and seated.  
4. Each player takes their turn with a **20s timer**.  
   - No action → auto-bust.  
5. Dealer plays out hand.  
6. Results shown → 5s pause → new round starts automatically.  
7. Queue continues cycling in.  

---
