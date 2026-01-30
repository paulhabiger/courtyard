# Castle Courtyard - Tactical Combat Game

A turn-based tactical combat game featuring an archer (player) vs. a knight (AI) in a randomized castle courtyard.

## 🎮 Features

- **Turn-based tactical combat** with strategic positioning
- **AI opponent** that uses stealth and cover tactics
- **Randomized courtyard layouts** - different map each game
- **Line of sight system** with obstruction detection
- **Movement tracking** - move before and after attacking
- **Sound effects** using Web Audio API
- **Procedural terrain generation** - walls, buildings, trees
- **A* pathfinding** for movement visualization
- **Bresenham's algorithm** for line of sight calculations

## 🏗️ Project Structure

```
castle-courtyard-project/
├── index.html          # Main game file (self-contained)
├── README.md          # This file
└── DEVELOPMENT.md     # Development guide
```

## 🚀 Quick Start

### Option 1: Direct Browser
Simply open `index.html` in any modern web browser.

### Option 2: Local Server (Recommended)
```bash
# Python 3
python -m http.server 8000

# Node.js
npx http-server

# Then open: http://localhost:8000
```

## 🎯 Game Mechanics

### Characters
- **Elara (Archer)** - Player controlled
  - HP: 50
  - Movement: 30 ft (6 squares)
  - Range: 40 ft (8 squares)
  - Damage: 8-15

- **Sir Gareth (Knight)** - AI controlled
  - HP: 80
  - Movement: 25 ft (5 squares)
  - Range: 5 ft (1 square)
  - Damage: 10-18

### Controls
- **Drag** to move your character
- **Attack** button appears when in range with line of sight
- **End Turn** to pass to opponent
- Movement is deducted as you move (displayed in real-time)
- Can move before AND after attacking

### Win Condition
First character to reach 0 HP loses!

## 🛠️ Technical Details

### Technologies
- Pure HTML5/CSS3/JavaScript (no frameworks)
- Canvas API for rendering
- Web Audio API for sound effects
- Procedural generation algorithms

### Algorithms Used
- **A* Pathfinding** - Optimal route calculation
- **Bresenham's Line** - Line of sight detection
- **BFS** - Movement range calculation
- **Random generation** - Courtyard layouts

### Key Components
1. **Grid System** - 25x20 tile battlefield
2. **Terrain Types** - Grass, walls, trees, stone floors, buildings
3. **Combat System** - Turn-based with movement tracking
4. **AI System** - Tactical decision making with cover preference
5. **Sound System** - Procedural audio generation

## 📝 Development

See `DEVELOPMENT.md` for detailed development instructions.

### Code Structure

The `index.html` file contains:
- CSS styling (lines 7-634)
- HTML structure (lines 636-810)
- JavaScript game logic (lines 812-2800+)

### Main Functions

**Core Game Loop:**
- `draw()` - Main render function
- `updateUI()` - Updates interface
- `endTurn()` - Handles turn switching

**Movement & Combat:**
- `getMovementRange()` - Calculates valid moves
- `findPath()` - A* pathfinding
- `hasLineOfSight()` - LOS checking
- `performAttack()` - Attack execution

**AI:**
- `knightAI()` - AI turn controller
- `evaluateKnightPosition()` - Position scoring
- `findBestKnightMove()` - Move selection

**Generation:**
- `generateCourtyard()` - Procedural map generation
- `findRandomStartingPositions()` - Character placement

## 🔊 Sound Effects

All sounds are procedurally generated using Web Audio API:
- **Move** - Soft movement beep
- **Arrow** - Whooshing projectile
- **Sword** - Metallic slash
- **Hit** - Impact sound
- **Victory** - Ascending fanfare
- **Defeat** - Descending tones

## 🎨 Art Style

Inspired by Final Fantasy Tactics with:
- Medieval fantasy theme
- Cinzel serif font for headers
- Golden/brown color palette
- Tactical grid overlay
- Detailed terrain rendering

## 📦 Deployment

The game is fully self-contained in a single HTML file. To deploy:

1. **GitHub Pages**: Upload `index.html`
2. **Netlify**: Drag and drop the file
3. **Vercel**: Deploy from repository
4. **Any static host**: Just upload the HTML file

## 🐛 Known Issues & Future Improvements

See the Issues section in the repository or check `DEVELOPMENT.md` for enhancement ideas.

## 📄 License

This project was created with Claude AI. Feel free to use and modify for personal or commercial projects.

## 🙏 Credits

- Game design and implementation: Claude AI + User collaboration
- Font families: Google Fonts (Cinzel, Philosopher)
- Inspiration: Final Fantasy Tactics, Fire Emblem

---

**Version:** 1.0.0  
**Last Updated:** January 2026
