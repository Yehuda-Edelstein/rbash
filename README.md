# rbash
A customizable React component that renders a terminal-like interface. It supports various built-in commands like `ls`, `help`, `clear`, while also providing an interface for custom commands.

<img alt="example" src="https://user-images.githubusercontent.com/92326059/234421648-9b0758d6-4a62-4d35-bfbb-e2c369761543.png" width="500" align="right">

## Usage
To use the rbash in your React project, you can install it from NPM by running `npm install rbash` and importing it:
```
import { Terminal } from 'rbash/main';

function App() {
  return (
    <div>
      <Terminal />
    </div>
  );
}
```
## Props
The `<Terminal />` component has 6 props that can all be edited:
- `branch = randomBranch() // if no branch is passed a random one will be selected` 
- `dirs = ["pass", "in", "your", "custom", "dirs"], // default list of directories`
- `cwd = "/rbash", // current working directory`
- `commands = {}, // custom commands`
- `bgColor = "#1e1e1e", // background color of terminal body`
- `color = "White", // font color`

It also has some built in commands:
```
builtInCommands = {
    clear: { cmd: "clear/cls", output: null, def: "clears terminal" },
    help: { cmd: "help", output: null, def: "shows list of available commands"},
    pwd: {cmd: "pwd", output: cwd, def: "outputs current working directory"},
    ls: {cmd: "ls", output: null, def: "lists contents of current working directory"},
    ...commands,
},
```
Note that while you can alter the `builtInCommands` it is not advisable to do so.

## Adding Custom Commands
To add custom commands, pass an object to the commands prop with the command name as the key and an object with the following properties as the value:
```
import Terminal from 'rbash/main';

function App() {
  const customCommands = {
    hello: {
      cmd: 'hello',
      def: 'Says hello to the user',
      output: 'Hello!',
    },
  };

  return (
    <div>
      <Terminal commands={customCommands} />
    </div>
  );
}
```

## Contributing
Bug reports and pull requests are welcome, feel free to contribute in any you can.
