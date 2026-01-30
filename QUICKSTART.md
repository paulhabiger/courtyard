# Quick Start - Castle Courtyard in Cursor IDE

## 🚀 Getting Started in Cursor

### 1. Open the Project

```bash
# In Cursor, use File > Open Folder
# Then select: castle-courtyard-project
```

### 2. Run the Game

**Option A: Simple (Double-click)**
- Just open `index.html` in your browser
- No server needed for basic functionality

**Option B: Local Server (Recommended)**

Using Python:
```bash
# In Cursor terminal (Ctrl + `)
python -m http.server 8000

# Then open: http://localhost:8000
```

Using npm:
```bash
npm run serve
# or
npm run dev  # With live reload
```

### 3. Make Changes

The entire game is in `index.html` - it's a single-file application for simplicity.

**Live Reload:**
- Save the file (Ctrl/Cmd + S)
- Refresh browser (F5)
- Changes appear instantly

## 📁 Project Structure

```
castle-courtyard-project/
├── index.html              # Main game file (everything is here!)
├── README.md              # Project overview
├── DEVELOPMENT.md         # Development guide
├── TODO.md               # Future enhancements
├── QUICKSTART.md         # This file
├── package.json          # npm configuration
├── .gitignore            # Git ignore rules
└── .vscode/
    └── extensions.json   # Recommended VS Code extensions
```

## 🔍 Finding Code in Cursor

Use **Cursor's AI Chat** (Ctrl/Cmd + L) to ask questions like:
- "Show me the AI decision logic"
- "Where is the movement system?"
- "How do I change character stats?"

Or use **Go to Symbol** (Ctrl/Cmd + Shift + O):
- Type function names: `draw`, `knightAI`, `generateCourtyard`
- Jump directly to code

## 🎯 Common Tasks

### Change Character Stats

1. Press Ctrl/Cmd + F
2. Search for: `ARCHER_MOVEMENT`
3. Modify the constants (around line 900)

### Modify AI Behavior

1. Use Cursor AI: "Show me the knight AI logic"
2. Or search for: `function knightAI()`
3. Adjust scoring in `evaluateKnightPosition()`

### Customize Colors

1. Search for: `:root` (CSS variables)
2. Or: `--color-archer`
3. Change hex values

## 💡 Using Cursor AI Features

### Chat with Your Code
Press **Ctrl/Cmd + L** and ask:
- "Explain how line of sight works"
- "How can I add a new attack animation?"
- "Show me all sound effect code"

### Code Generation
Select code, then:
- **Ctrl/Cmd + K**: Generate related code
- Type what you want: "Add a shield blocking mechanic"

### Quick Edits
- **Ctrl/Cmd + K**: Inline AI editing
- Highlight code and describe changes

## 🐛 Debugging

### Console Logs
Add anywhere in JavaScript:
```javascript
console.log('Movement used:', movementUsedThisTurn);
```

View in browser: F12 > Console tab

### Cursor's Debugger
1. Right-click `index.html`
2. "Debug with Chrome"
3. Set breakpoints by clicking line numbers

## 📊 Key Functions to Know

Quick reference for editing:

```javascript
// Main game loop
function draw()              // Renders everything
function updateUI()          // Updates interface
function endTurn()           // Switches turns

// Movement & Combat
function getMovementRange()  // Valid move tiles
function hasLineOfSight()    // Can see target?
function performAttack()     // Execute attack

// AI
function knightAI()          // AI controller
function evaluatePosition()  // Position scoring

// Map
function generateCourtyard() // Creates random map
```

## 🎨 Styling Tips

All CSS is at the top of `index.html`:
- Lines 7-634: All styles
- Use Cursor AI: "Change the archer's color to green"
- Or manually edit CSS variables

## 🚢 Deploying Your Changes

### GitHub Pages
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin [your-repo-url]
git push -u origin main

# Enable GitHub Pages in repo settings
```

### Netlify
1. Drag `index.html` to netlify.com/drop
2. Done! Live in seconds

### Vercel
```bash
npx vercel
```

## 🤖 Cursor AI Prompts to Try

Copy these into Cursor AI chat:

```
"Add a new terrain type: water that slows movement"

"Create a special attack for the archer: explosive arrow that damages in a 2-tile radius"

"Add a skill tree system where characters level up"

"Implement a replay system to watch the last battle"

"Add particle effects when attacks land"

"Create a dark mode toggle"
```

## 📚 Learning Resources

- **Pathfinding**: Search "A* algorithm" in code
- **Line of Sight**: Search "Bresenham"
- **AI**: Look at `evaluateKnightPosition()`
- **Canvas**: MDN Canvas API docs

## 💬 Getting Help

When asking Cursor AI for help:
1. Be specific: "How do I add a heal ability that restores 20 HP?"
2. Reference existing code: "Using the same pattern as performAttack()"
3. Ask for examples: "Show me an example implementation"

## ✅ Verification Checklist

After making changes:
- [ ] Save file (Ctrl/Cmd + S)
- [ ] Refresh browser (F5)
- [ ] Check console for errors (F12)
- [ ] Test the feature
- [ ] Works as expected!

---

**Pro Tip:** Cursor's AI is great at explaining existing code. Select any function and ask "What does this do?" to understand before modifying.

Happy coding! 🎮⚔️
