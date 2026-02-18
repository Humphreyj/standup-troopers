# 🎮 Standup Troopers

A fun top-down auto battler game to pick the next standup leader!

## 🎯 How It Works

Participants fight cartoon bugs with laser guns in an arena. The size of the horde increases over time, overwhelming the characters. The last one standing becomes the next standup leader!

## 🚀 Getting Started

1. Open `index.html` in a web browser
2. Add participants using the text input
3. Click "Start Battle!" when ready (minimum 2 participants)
4. Watch the auto-battle unfold
5. The winner is declared as the next standup leader!

## 🎨 Features

- **Setup Screen**: Add/remove participants with a clean UI
- **Player Characters**: Green circles with names displayed above them
- **Direction Indicators**: White arrows showing which way characters are facing
- **Enemy System**: Red circles (bugs) that spawn from the screen edges
- **Progressive Difficulty**: Enemy spawn rate and count increase over time
- **Health Bars**: Visual health indicators for all entities
- **Projectile System**: Yellow laser shots fired automatically by players
- **AI Behavior**: Players move and shoot autonomously
- **Winner Screen**: Displays the last survivor as the next standup leader
- **Play Again**: Reset functionality to start a new game

## 🛠️ Technical Details

- Single-file HTML5 Canvas game
- Vanilla JavaScript (no external dependencies)
- Responsive 1200x800 game canvas
- Frame-independent timing for consistent gameplay
- Collision detection for projectiles and enemies
- Progressive difficulty scaling

## 🔒 Security

- XSS protection through DOM manipulation instead of innerHTML
- Safe handling of participant names with special characters

## 📝 Development

To run locally:
```bash
python3 -m http.server 8000
# Then open http://localhost:8000/index.html
```

Or simply open `index.html` directly in your browser.

## 🎲 Game Mechanics

- Players spawn in a circle around the center
- Each player has 100 health points
- Players automatically move away from enemies
- Players automatically shoot at the nearest enemy
- Enemies spawn from screen edges and chase players
- Enemies deal 10 damage on contact (and die)
- Projectiles deal 25 damage to enemies
- Enemies have 50 health points
- Difficulty increases at 10s, 30s, and 60s marks

---

*May the best trooper win!* 🏆
