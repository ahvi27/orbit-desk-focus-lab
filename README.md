# ◉ Orbit Desk

A personal productivity website that combines a focus timer,
a task checklist, and daily activity statistics in one simple dashboard.

## Features

- 25-minute focus timer
- 5-minute short breaks
- 15-minute long breaks
- Start, pause, resume, and reset controls
- Add, complete, and delete tasks
- Task completion progress bar
- Daily completed focus sessions and focus minutes
- Daily completed task count
- Light and dark themes
- Browser storage for tasks, theme, and session statistics
- Responsive layout for mobile and desktop
- Keyboard-accessible controls
- No frameworks, dependencies, or build tools

## Technologies

- HTML5
- CSS3
- JavaScript
- Local Storage API

## Project Structure

```text
orbit-desk-focus-lab/
├── index.html
└── README.md
```

## Getting Started

1. Download or clone the repository.
2. Open `index.html` in your browser.
3. Add your tasks and start a focus session.

For a local development server with Python installed:

```bash
python3 -m http.server 8000
```

Then open:

```text
http://localhost:8000
```

## How to Use

1. Add a task under **Today's mission**.
2. Select **Focus**, **Short break**, or **Long break**.
3. Click **Start session**.
4. Pause or reset the timer whenever needed.
5. Check off tasks as you finish them.
6. View your daily statistics below the dashboard.

Switching timer modes resets the current timer.

## Data and Timer Behavior

Tasks, theme preferences, and completed session statistics are stored
in the current browser. They are not synced between devices.

Daily statistics follow your device's local date.
Tasks remain on the checklist until deleted.

Focus minutes count completed 25-minute focus sessions only.
Paused, reset, and unfinished sessions do not contribute minutes.

The timer uses a deadline to account for delayed browser updates.
Keep the page open for sessions to be recorded. Refreshing or closing
the page resets the active timer.

Clearing browser storage removes saved data. If storage is blocked,
the app works for the current visit without saving changes.

## Customization

Edit the CSS variables in `index.html` to change the colors.

Edit the `durations` object in the script to change timer lengths.
If you change the focus duration, also update the button label and
the focus-minute calculation.

## Deployment

Publish `index.html` on any static website host.
No build command or backend is required.

## Future Ideas

- Custom timer durations
- Optional completion sounds
- Task categories
- Weekly activity charts
- Data export and import
