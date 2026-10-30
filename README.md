# ◉ Orbit Desk — Focus Lab

A responsive productivity dashboard built with HTML, CSS, and JavaScript.
Organize tasks, run focus sessions, and track your daily progress.

## Features

### Focus Timer

- Focus, short-break, and long-break modes
- Default durations of 25, 5, and 15 minutes
- Custom durations from 1 to 180 minutes
- Start, pause, resume, and reset controls
- Saved timer state across page refreshes
- Deadline-based timing to handle delayed browser updates
- Optional completion sound
- Remaining time displayed in the browser tab

### Mission Board

- Add, edit, complete, and delete tasks
- High, normal, and low priorities
- Active tasks displayed before completed tasks
- Higher-priority tasks displayed first
- Search tasks by text
- Filter all, active, or completed tasks
- Clear completed tasks with confirmation
- Task completion progress bar

### Personal Workspace

- Light and dark themes
- Responsive mobile and desktop layouts
- Daily focus-session count
- Daily completed focus minutes
- Daily task-completion count
- Local browser storage
- JSON backup export and import
- Confirmation before importing replacement data
- Import validation and file-size limits

## Technology Stack

- HTML5
- CSS3
- Vanilla JavaScript
- Local Storage API
- Web Audio API
- Blob and File APIs

No frameworks, packages, backend, or build process are required.

## Project Structure

```text
orbit-desk-focus-lab/
├── index.html
└── README.md
```

## Run Locally

Download the files and open `index.html` in your browser.

For more consistent browser storage behavior, use a local server:

```bash
python3 -m http.server 8000
```

Visit:

```text
http://localhost:8000
```

## Using the Timer

1. Select Focus, Short break, or Long break.
2. Click Start session.
3. Pause and resume whenever needed.
4. Click Reset to restart the selected mode.

Switching modes resets the current timer.

To customize durations:

1. Open Timer settings.
2. Enter whole-number durations between 1 and 180 minutes.
3. Optionally enable the completion sound.
4. Click Save settings & reset timer.

Saving settings resets the current timer.

## Managing Tasks

1. Enter a mission.
2. Choose a priority.
3. Click Add.
4. Check the task when finished.
5. Use Edit to change its text or × to delete it.

Use search and filters to find tasks.

Clear completed deletes completed tasks after confirmation.
Deleting tasks does not subtract from the daily completion counter.

## Daily Statistics

Statistics use your device's local calendar date.

- Focus sessions counts completed focus timers.
- Focus minutes adds the full duration of each completed focus session.
- Tasks finished counts task completion actions during the day.

Checking the same task again after unchecking it counts as another
completion action.

Paused, reset, and unfinished focus sessions do not add focus minutes.
Breaks do not count as focus sessions.

Daily counters reset when the app detects a new local date.
Tasks remain until deleted.

## Timer Persistence

Timer state is saved when you start, pause, reset, switch modes,
or update settings.

A running timer uses a saved deadline. After refreshing or reopening
the page, the app calculates the remaining time.

If the deadline has passed, the app records the completion when reopened.
A focus session contributes to today's statistics only when its
completion deadline falls on today's local date.

The page does not run background notifications while closed.
Completion sounds depend on browser audio permissions and may not play
while the page is hidden or after reopening it.

Avoid changing your device clock during a session.

## Backups

### Export

Click Export JSON to download tasks, preferences, statistics,
and the current timer state.

The exported timer is paused. Exporting does not pause the live timer.

### Import

1. Click Import JSON.
2. Select an Orbit Desk version 2 backup smaller than 3 MB.
3. Confirm replacement of the current workspace.

Imported timers restore as paused.

Imports replace existing data; they do not merge task lists.

## Storage and Privacy

Data is stored in the current browser for the current website address.
The app has no backend and sends no workspace data to a server.

Data does not automatically sync across browsers or devices.
Use export and import to transfer your workspace.

Clearing browser storage removes saved data.
If browser storage is unavailable or full, changes may only last
for the current visit. Export a backup before leaving.

Version 2 uses a separate storage key from the original version.
Old version 1 data is not automatically migrated.

Use one active tab for the same workspace to avoid conflicting saves.

## Accessibility

- Labeled form controls
- Visible keyboard focus indicators
- Native buttons and checkboxes
- Timer-mode selection states
- Status announcements
- Responsive layouts

Task editing and destructive-action confirmations use native browser
dialogs.

## Customization

Edit the CSS variables near the top of `index.html` to change colors.

Edit `freshState()` to change defaults for new workspaces.

Existing saved preferences take priority over changed defaults.
Update settings in the interface or clear the saved workspace
to apply new defaults.

## Deployment

Upload `index.html` to a static website host.

No build command, package installation, or backend is needed.
Keep `index.html` at the root of the published directory.

## Possible Future Improvements

- Weekly statistics and charts
- Due dates and task categories
- Inline task editing
- Optional automatic break transitions
- Cross-device synchronization
- Installable PWA support
