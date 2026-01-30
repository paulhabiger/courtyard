# TODO - Castle Courtyard

## 🐛 Bug Fixes

- [ ] Fix movement sound playing too frequently during drag
- [ ] Ensure AI can't get stuck in unreachable positions
- [ ] Add validation for edge cases in pathfinding
- [ ] Handle window resize for canvas scaling

## ✨ Features to Add

### High Priority

- [ ] **Save/Load Game State**
  - Save to localStorage
  - Resume interrupted battles
  - Game history

- [ ] **Difficulty Settings**
  - Easy: AI makes random moves occasionally
  - Normal: Current behavior
  - Hard: AI looks ahead multiple turns

- [ ] **More Character Abilities**
  - Archer: Multi-shot, trap placement
  - Knight: Shield block, charge attack
  - Cooldown system for abilities

### Medium Priority

- [ ] **Multiple Maps**
  - Forest clearing
  - Castle interior
  - Desert ruins
  - Map selection menu

- [ ] **Character Customization**
  - Choose character names
  - Select color schemes
  - Unlock cosmetic items

- [ ] **Tutorial Mode**
  - Step-by-step guide
  - Highlighted UI elements
  - Practice scenarios

- [ ] **Stats Tracking**
  - Win/loss record
  - Average damage dealt
  - Turns per game
  - Display in stats screen

### Low Priority

- [ ] **Mobile Touch Controls**
  - Better touch detection
  - Zoom/pan on small screens
  - Portrait mode optimization

- [ ] **Accessibility**
  - Keyboard controls
  - Screen reader support
  - High contrast mode
  - Colorblind modes

- [ ] **Achievements**
  - "Perfect Victory" - Win without taking damage
  - "Sharpshooter" - Win with only ranged attacks
  - "Close Combat" - Win only using melee
  - Achievement notification system

## 🎨 Polish

- [ ] Better hit animations
- [ ] Particle effects for attacks
- [ ] Character idle animations
- [ ] Smooth camera pan to actions
- [ ] Victory/defeat screen animations
- [ ] Background music (optional toggle)
- [ ] Better loading screen

## 🔧 Technical Improvements

- [ ] **Code Organization**
  - Split into modules (game.js, ai.js, rendering.js)
  - Use ES6 modules
  - Better separation of concerns

- [ ] **Performance**
  - Cache frequently used calculations
  - Optimize rendering (dirty rectangles)
  - Web Worker for AI calculations

- [ ] **Testing**
  - Unit tests for algorithms
  - Integration tests for game flow
  - AI behavior tests

- [ ] **Documentation**
  - Inline code comments
  - JSDoc for functions
  - Architecture diagrams

## 🌐 Multiplayer (Future)

- [ ] **Local Multiplayer**
  - Hot-seat mode
  - Same device, turn-based

- [ ] **Online Multiplayer**
  - WebSocket server
  - Room creation
  - Matchmaking
  - Spectator mode

## 💡 Experimental Ideas

- [ ] **Procedural character generation**
  - Random stat distributions
  - Different character classes
  - Equipment system

- [ ] **Fog of war**
  - Limited visibility
  - Reveal tiles as you move
  - Strategic positioning

- [ ] **Environmental hazards**
  - Fire spreads across tiles
  - Water slows movement
  - High ground advantage

- [ ] **Campaign mode**
  - Story progression
  - Character leveling
  - Equipment upgrades
  - Multiple enemy types

---

## 📋 Completed

- [x] Basic combat system
- [x] AI opponent
- [x] Movement tracking
- [x] Line of sight
- [x] Pathfinding visualization
- [x] Sound effects
- [x] Random map generation
- [x] Splash screen
- [x] Victory/defeat screens
- [x] Move before/after attack
- [x] Continuous movement deduction
