# ToDo App

This is a simple ToDo app built with Vanilla TypeScript and Vite.

## Features

- ✅ Add new tasks with a simple input field
- ✅ Mark tasks as completed with visual feedback
- ✅ Delete tasks with a single click
- ✅ **NEW:** Gray text styling for completed items (improves visual distinction)
- ✅ Persistent storage using localStorage
- ✅ Responsive design with accessibility support

## Installation

1. Clone the repository:

   ```
   git clone https://github.com/xkalepar/todo-list-typescript
   ```

2. Navigate to the project directory:

   ```
   cd todo-app
   ```

3. Install the dependencies:

   ```
   npm install
   ```

## Usage

1. Start the development server:

npm run dev

```
   This will start the app and automatically open it in your default browser.
```

2. Interact with the app in your browser:

- Add new tasks by entering text in the input field and pressing Enter.
- Click on a task to mark it as completed.
- Click on the "X" button next to a task to delete it.

## Recent Updates

### Gray Text for Completed Items (November 2025)
Completed todo items now appear with gray text color (#999), making it easier to visually distinguish between active and completed tasks. This enhancement:
- Maintains WCAG AA accessibility with 5.9:1 contrast ratio
- Uses existing CSS patterns (no JavaScript changes)
- Provides clear visual feedback without compromising readability

See the [implementation documentation](../grey-text-completed-items.md) for technical details.

## Make changes to the code:

You can modify the TypeScript files in the src directory to customize the app according to your needs. For guidance on maintaining consistency with the project's patterns, see the [Copilot Instructions](../.github/copilot-instructions.md).

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

```
This project is licensed under the MIT License.
```
## Live Demo

Check out the live demo of the ToDo app <a href="https://awesome-todo-list-nkq0.onrender.com/" target="_blank">here</a>.
