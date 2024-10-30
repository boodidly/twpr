# Mate Terminal Wrapper

A Node.js wrapper for MATE Terminal that provides a simple API to programmatically control terminal instances.

## Prerequisites

```bash
sudo pacman -S mate-terminal nodejs npm
```

## Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd mate-terminal-wrapper
```

2. Install dependencies:
```bash
npm install
```

## Usage

```javascript
const MateTerminal = require('./mate-terminal.js');
const terminal = new MateTerminal();

// Open a basic terminal
terminal.open({
  title: 'My Terminal',
  command: 'ls -la',
  workingDirectory: process.cwd(),
  geometry: '80x24',
  zoom: 1.0
});

// Quick command execution
terminal.openWithCommand('htop');

// Open in specific directory
terminal.openInDirectory('/home/user');

// Open in fullscreen mode
terminal.openFullscreen('vim');
```

## API Reference

### `open(options)`

Opens a new terminal window with specified options:

- `title`: Window title
- `command`: Command to execute
- `workingDirectory`: Starting directory
- `profile`: Terminal profile name
- `geometry`: Window size (e.g., '80x24')
- `zoom`: Zoom level (e.g., 1.0)
- `fullscreen`: Boolean to start in fullscreen
- `maximize`: Boolean to start maximized

### Helper Methods

- `openWithCommand(command)`: Open terminal with specific command
- `openInDirectory(directory)`: Open terminal in specific directory
- `openFullscreen(command)`: Open terminal in fullscreen mode

## Development

To run the example:

```bash
npm start
```

## Troubleshooting

1. If you get permission errors:
   ```bash
   # Check if mate-terminal is installed
   which mate-terminal
   
   # Verify executable permissions
   ls -l $(which mate-terminal)
   ```

2. If Node.js can't find the module:
   ```bash
   # Verify node_modules exists
   ls node_modules
   
   # Reinstall dependencies
   rm -rf node_modules
   npm install
   ```

## License

MIT

## Contributing

1. Fork the repository
2. Create your feature branch
3. Commit your changes
4. Push to the branch
5. Create a Pull Request