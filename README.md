# Abstract Game Framework

A JavaScript-based abstract platform for creating interactive games with geometric shapes, animations, and user interactions.

## Overview

This framework provides a modular architecture for building 2D games using HTML5 Canvas. It supports various geometric shapes (circles, rectangles, triangles), movement systems with physics, collision detection, and user input handling.

## Project Structure

The project is organized into three development phases, each building upon the previous:

```
abstract_game/
├── phase01/          # Basic framework with modular components
├── phase02/          # Simplified unified framework
├── phase03/          # Advanced framework with ball game demo
└── README.md
```

## Phase Development

### Phase 01 - Modular Framework
**Files:** `frameworkMap.js`, `frameworkPaintware.js`, `frameworkPaintspace.js`, `frameworkForm.js`, `adaptor.js`, `adaptorConfig.js`

- Highly modular architecture with separate components
- Basic shape rendering (circles, rectangles, triangles)
- Mouse and keyboard event handling
- Canvas-based rendering system

### Phase 02 - Unified Framework
**Files:** `framework.js`, `adaptor.js`

- Consolidated framework with `Widget` and `Paintspace` classes
- Enhanced movement system with vector-based physics
- Border collision detection and effects
- Simplified API for game development

### Phase 03 - Advanced Framework with Game Demo
**Files:** `framework.js`, `adaptor.js`, `ballGame.js`

- Advanced `Widget` and `Widgets` classes
- Sophisticated movement system with border effects (stop, bounce)
- Complete ball avoidance game implementation
- Enhanced collision detection

## Core Features

### Shape Support
- **Circle**: Defined by center coordinates and radius
- **Rectangle**: Defined by position and dimensions
- **Triangle**: Defined by three vertex coordinates

### Movement System
- Vector-based movement with magnitude and direction
- Border collision detection
- Configurable border effects:
  - `effectStop`: Stop movement at borders
  - `effectBounce`: Bounce off borders

### Input Handling
- Mouse movement and click events
- Keyboard input with predefined key constants
- Real-time interaction support

### Canvas Rendering
- HTML5 Canvas-based graphics
- Customizable colors and styles
- Automatic refresh and animation loop

## Quick Start

### Running Phase 03 (Ball Game)
1. Open `phase03/index.html` in a web browser
2. Move your mouse to control the yellow avatar
3. Avoid the bouncing colored balls
4. Game ends when avatar touches any ball

### Basic Usage Example

```javascript
// Create a widget (circle)
var ball = new Widget([100, 100, 50, 150], ShapeCircle, "red");

// Set movement vector (speed: 15, angle: π/4)
ball.setMove([15, Math.PI/4], [400, 400], effectBounce);

// Game loop
function update() {
    ball.move();
    ball.draw();
}
```

## API Reference

### Widget Class
```javascript
// Constructor
new Widget(positions, shape, color)

// Methods
widget.setMove(vector, space, borderEffect)  // Set movement parameters
widget.move()                                // Update position
widget.draw()                                // Render to canvas
widget.isClicked(x, y)                      // Check if point is inside widget
```

### Shape Constants
- `ShapeCircle = 0`
- `ShapeRectangle = 1` 
- `ShapeTriangle = 2`

### Border Effects
- `effectNone = -1`
- `effectStop = 0`
- `effectBounce = 1`

### Key Constants
Predefined constants for keyboard input:
- Arrow keys: `K_LEFT`, `K_RIGHT`, `K_UP`, `K_DOWN`
- Letters: `K_A` through `K_Z`
- Numbers: `K_0` through `K_9`
- Special: `K_SPACE`, `K_ESC`

## Game Development

### Creating a New Game
1. Choose a phase as your starting point
2. Modify the game logic in the respective test/game file
3. Customize shapes, colors, and movement patterns
4. Implement game-specific event handlers

### Event Handlers
```javascript
function mouseMove(x, y) { /* Handle mouse movement */ }
function mouseClick(x, y) { /* Handle mouse clicks */ }
function keyDown(keyCode) { /* Handle keyboard input */ }
function update() { /* Main game loop */ }
```

## Browser Compatibility

- Modern browsers with HTML5 Canvas support
- Chrome, Firefox, Safari, Edge
- Mobile browsers supported

## Development Notes

- Phase 01 demonstrates modular architecture principles
- Phase 02 shows framework consolidation and optimization
- Phase 03 provides a complete game implementation example
- Each phase can be studied independently for different architectural approaches

## Contributing

When extending the framework:
1. Maintain backward compatibility where possible
2. Follow the established naming conventions
3. Test across different browsers
4. Document new features and APIs

## License

This project is provided as-is for educational and development purposes.