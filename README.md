# 🎮 Standup Troopers

A fun top-down auto battler game to pick the next standup leader!

## 🎯 How It Works

Participants fight cartoon bugs with laser guns in an arena. The size of the horde increases over time, overwhelming the characters. The last one standing becomes the next standup leader!

## 🚀 Getting Started

1. Open `index.html` in a web browser
2. Add participants using the text input (or use the pre-populated team)
3. Click "Start Battle!" when ready (minimum 2 participants)
4. Watch the auto-battle unfold with music and sound effects
5. The winner is declared with their bug kill count!

## 🎨 Features

### Core Gameplay

- **Full Viewport Canvas**: Game fills the entire browser window
- **Setup Screen**: Add/remove participants with a clean UI
- **Player Characters**: Green circles with names and health bars
- **Direction Indicators**: White arrows showing which way characters are facing
- **AI Behavior**: Players move autonomously, kite enemies, and collect powerups
- **Collision Avoidance**: Friendly units maintain spacing to prevent overlap
- **Kill Tracking**: Each player's enemy kills are tracked and displayed

### Enemy Types

- **Standard Enemy** (Red): Basic melee enemy (50 HP, 10 damage, 1.5 speed)
- **Tank Enemy** (Dark Red): Slow, heavily armored (120 HP, 20 damage, 0.8 speed, larger size)
- **Scout Enemy** (Light Red): Fast, fragile (25 HP, 5 damage, 3.125 speed, smaller size)
- **Spitter Enemy** (Purple): Ranged attacker that shoots projectiles (40 HP, 15 damage per shot, 1.0 speed)
- **Blinker Enemy** (Pink): Area damage on contact, visually blinks (50 HP, 10 damage in 100px radius, 1.5 speed)

### Powerup System

All powerups last 10 seconds and spawn from defeated enemies:

- **Health Pack** (Green, 5% drop): Heals 5-10% of max health
- **Rapid Fire** (Orange, 6% drop): Increases fire rate by 60%
- **Shotgun** (Red, 6% drop): Fires 5 projectiles in a spread pattern with higher damage
- **Big Bullet** (Gold, 6% drop): Doubles projectile size and damage, stacks up to 2 times (4x at max)

### Progressive Difficulty

- **Starting**: 3 enemies every 1.5 seconds
- **10 seconds**: 5 enemies every 1.2 seconds
- **30 seconds**: 7 enemies every 1 second
- **60 seconds**: 9 enemies every 0.8 seconds
- **60+ seconds**: Special enemy spawn rates double, all enemies gain 10% speed boost

### Audio

- **Background Music**: Slider.mp3 plays during battle
- **Wilhelm Scream**: Plays when players die (reduced volume for comedy)
- **Victory Music**: Plays when the winner is announced

## 🛠️ Technical Details

- Single-file HTML5 Canvas game
- Vanilla JavaScript (no external dependencies)
- Dynamic canvas sizing (fills viewport)
- Frame-independent timing for consistent gameplay
- Advanced collision detection (projectiles, enemies, powerups, friendly units)
- Progressive difficulty scaling with time-based mechanics
- Audio system with multiple sound effects

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

## � Detailed Game Mechanics

### Player Stats

- **Health**: 120 HP
- **Speed**: 2 units/frame
- **Fire Rate**: 500ms base (affected by Rapid Fire powerup)
- **Projectile Damage**: 25 base (affected by Big Bullet powerup)
- **Projectile Speed**: 8 units/frame
- **Radius**: 20 pixels

### Enemy Spawn Rates

- **Standard**: 61% (22% after 60s)
- **Tank**: 12% (24% after 60s)
- **Scout**: 18% (36% after 60s)
- **Spitter**: 6% (12% after 60s)
- **Blinker**: 3% (6% after 60s)

### Combat Mechanics

- Players automatically target and shoot the nearest enemy
- Players kite enemies while maintaining optimal combat distance
- Players actively seek nearby powerups (within 250 pixels)
- Shotgun fires 5 pellets in a 22.5-degree spread (35 damage each, 300 range)
- Big Bullet stacks multiplicatively (2x → 4x size and damage)
- Rapid Fire and Shotgun can be active simultaneously
- Friendly fire is disabled

### AI Behavior

- **Close Range** (<250px): Kite away while circle strafing
- **Medium Range** (250-400px): Circle strafe around enemies
- **Long Range** (>400px): Move toward center to stay in action
- **Powerup Priority**: Move toward nearby powerups when available
- **Separation**: Maintain spacing from friendly units to prevent overlap

---

_May the best trooper win!_ 🏆
