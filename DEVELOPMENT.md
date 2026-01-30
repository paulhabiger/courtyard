# Development Guide - Castle Courtyard

This guide helps you navigate and modify the codebase in Cursor IDE.

## 📂 File Organization

The entire game is in `index.html` for simplicity. Here's the structure:

### Section Breakdown

1. **Lines 1-634: CSS Styles**
   - Root variables (colors, sizes)
   - Component styles (cards, buttons, overlays)
   - Animations and transitions
   - Responsive media queries

2. **Lines 636-810: HTML Structure**
   - Game board container
   - Info panel (character cards, stats)
   - Game over overlay
   - Splash screen

3. **Lines 812-2800+: JavaScript Game Logic**
   - Configuration and constants
   - Sound system
   - Map generation
   - Game state management
   - Algorithms (pathfinding, LOS)
   - AI logic
   - Event handlers
   - UI updates

## 🎯 Common Modifications

### Changing Character Stats

**Location:** Lines ~900-910

```javascript
const ARCHER_MOVEMENT = 6;  // 30 feet (each square = 5ft)
const ARCHER_RANGE = 8;     // 40 feet
const ARCHER_DAMAGE = { min: 8, max: 15 };

const KNIGHT_MOVEMENT = 5;  // 25 feet
const KNIGHT_RANGE = 1;     // 5 feet
const KNIGHT_RANGE = { min: 10, max: 18 };
```

### Adjusting AI Difficulty

**Location:** Function `evaluateKnightPosition()` (~1200-1280)

Modify scoring weights:
```javascript
// Increase for more aggressive AI
score += 1000; // Melee range priority

// Increase for more defensive AI
score += 200; // Stealth bonus

// Modify danger penalty
score -= 300; // Visible in archer range
```

### Customizing Map Generation

**Location:** Function `generateCourtyard()` (~950-1050)

```javascript
// Change number of buildings
const numBuildings = 1 + Math.floor(Math.random() * 2); // 1-2 buildings

// Change number of trees
const numTrees = 12 + Math.floor(Math.random() * 9); // 12-20 trees

// Adjust gate positions
const gateTop = 8 + Math.floor(Math.random() * 6);
```

### Adding New Sound Effects

**Location:** Function `playSound()` (~860-950)

Add new case to switch statement:
```javascript
case 'newSound':
  oscillator.type = 'sine';
  oscillator.frequency.value = 440;
  gainNode.gain.setValueAtTime(0.2, audioContext.currentTime);
  gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.5);
  oscillator.start(audioContext.currentTime);
  oscillator.stop(audioContext.currentTime + 0.5);
  break;
```

### Changing Grid Size

**Location:** Lines ~806-810

```javascript
const GRID_WIDTH = 25;  // Horizontal tiles
const GRID_HEIGHT = 20; // Vertical tiles
const CELL_SIZE = 45;   // Pixels per tile
```

**Note:** Changing grid size requires adjusting wall generation in `generateCourtyard()`

## 🔧 Key Systems Explained

### 1. Movement System

Movement is tracked from turn start position:

```javascript
// Turn start position stored in:
archer.startX, archer.startY
knight.startX, knight.startY

// Movement used this turn:
movementUsedThisTurn = getDistance(turnStartPos, currentPos);
```

### 2. Line of Sight

Uses Bresenham's algorithm:

```javascript
function hasLineOfSight(start, end) {
  // Traces grid line between points
  // Returns false if wall/tree encountered
  // Returns true if clear path
}
```

### 3. Pathfinding

A* algorithm implementation:

```javascript
function findPath(start, end) {
  // Returns array of {x, y} points
  // Empty array if no path exists
  // Uses Manhattan + diagonal distance heuristic
}
```

### 4. AI Decision Making

Three-step process:

```javascript
1. knightAI() - Main controller
2. findBestKnightMove() - Evaluates all possible moves
3. evaluateKnightPosition() - Scores each position
```

Scoring factors:
- Distance to archer (closer = better)
- Cover availability (hidden = better)
- Melee range (attack opportunity = best)
- Escape routes (more options = better)

## 🎨 Styling Customization

### Color Scheme

**Location:** Lines 10-26 (CSS :root)

```css
--color-archer: #3498db;     /* Blue */
--color-knight: #c0392b;     /* Red */
--color-accent: #d4af37;     /* Gold */
--color-bg: #2b1810;         /* Dark brown */
```

### Fonts

**Location:** Line 8 (Google Fonts import)

```css
@import url('https://fonts.googleapis.com/css2?family=Cinzel:wght@400;600;700&family=Philosopher:wght@400;700&display=swap');
```

Current fonts:
- **Cinzel** - Medieval serif for titles
- **Philosopher** - Sans-serif for body text

### Terrain Colors

**Location:** Function `drawTerrain()` (~1400-1600)

Modify fill colors:
```javascript
case 0: // Grass
  ctx.fillStyle = '#4a6741';
  
case 1: // Wall
  ctx.fillStyle = '#5c4a3a';
  
case 2: // Tree
  ctx.fillStyle = '#2d4a2d';
```

## 🐛 Debugging Tips

### Enable Console Logging

Add debug logs to track game state:

```javascript
function endTurn() {
  console.log('Turn ending:', currentTurn);
  console.log('Movement used:', movementUsedThisTurn);
  console.log('Has attacked:', hasAttacked);
  // ... rest of function
}
```

### Visual Debugging

Show hitboxes and ranges:

```javascript
// In draw() function, add:
ctx.strokeStyle = 'red';
ctx.strokeRect(archer.x * CELL_SIZE, archer.y * CELL_SIZE, CELL_SIZE, CELL_SIZE);
```

### Performance Monitoring

```javascript
// At start of draw()
const startTime = performance.now();

// At end of draw()
console.log('Draw time:', performance.now() - startTime, 'ms');
```

## 📊 Game State Variables

Critical state tracked:

```javascript
archer = { x, y, hp, maxHp, startX, startY }
knight = { x, y, hp, maxHp, startX, startY }
currentTurn = 'archer' | 'knight'
movementUsedThisTurn = 0-6 (archer) or 0-5 (knight)
hasAttacked = true | false
isAnimating = true | false
aiThinking = true | false
isDragging = true | false
grid = 2D array of terrain types
```

## 🚀 Extension Ideas

### Easy Extensions

1. **Add more characters**
   - Create new character objects
   - Add to character selection

2. **New terrain types**
   - Add case to `drawTerrain()`
   - Update `generateCourtyard()`

3. **Power-ups**
   - Add items to grid
   - Create pickup system

### Medium Extensions

1. **Multiplayer**
   - Replace AI with second player
   - Add turn indicator

2. **Campaign mode**
   - Multiple battles
   - Character progression
   - Save/load system

3. **More abilities**
   - Special attacks
   - Cooldown system
   - Ability UI

### Advanced Extensions

1. **Network multiplayer**
   - WebSocket server
   - Game state sync
   - Matchmaking

2. **Map editor**
   - Click to place terrain
   - Save/load custom maps
   - Share maps

3. **Advanced AI**
   - Machine learning
   - Behavior trees
   - Difficulty levels

## 🔍 Code Navigation Tips for Cursor

Use these search terms to quickly find code:

- `function draw()` - Main render loop
- `function updateUI()` - UI updates
- `function knightAI()` - AI logic
- `function generateCourtyard()` - Map generation
- `canvas.addEventListener` - Event handlers
- `playSound(` - Sound effects
- `class="` - CSS component search
- `getElementById` - DOM element access

## 📝 Testing Checklist

Before committing changes:

- [ ] Game loads without errors
- [ ] Archer can move and attack
- [ ] Knight AI takes turns
- [ ] Turn switching works
- [ ] Movement deduction is accurate
- [ ] Attack button shows/hides correctly
- [ ] Victory/defeat screens work
- [ ] Sound effects play
- [ ] Responsive on mobile
- [ ] No console errors

## 🤝 Contributing Workflow

1. Make changes in Cursor
2. Test in browser (refresh to reload)
3. Check console for errors
4. Test edge cases
5. Update documentation if needed

---

Happy coding! 🎮⚔️
