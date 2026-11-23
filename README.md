# trainee

A lightweight, mobile-first workout timer built with plain HTML, CSS and JavaScript. No build step or npm dependencies are required.

## Add a workout

1. Create a JSON file inside `workouts/`, for example `workouts/stretch.json`.
2. Add its filename to `workouts/index.json`.
3. Commit and push. GitHub Actions deploys the updated site automatically.

### Workout format

```json
{
  "id": "stretch",
  "name": "Stretch",
  "description": "A short mobility session",
  "icon": "activity",
  "exercises": [
    {
      "name": "Shoulder Rolls",
      "instruction": "Roll your shoulders slowly.",
      "duration": 30,
      "rest": 15
    },
    {
      "name": "Side Stretch",
      "instruction": "Stretch gently on both sides.",
      "duration": 40,
      "rest": 0
    }
  ]
}
```

- `id`: unique identifier for the workout.
- `name`: title shown in the workout gallery.
- `description`: optional description for future use.
- `icon`: optional Lucide icon key.
- `exercises`: ordered list of workout steps.
- `duration`: exercise duration in seconds for timed exercises.
- `type: "reps"`: optional; makes the exercise repetition-based instead of timer-based.
- `reps`: target number of repetitions for a repetition-based exercise.
- `secondsPerRep`: optional; enables automatic counting at the given seconds per repetition. Without it, the user counts each repetition manually.
- `rest`: rest after this exercise in seconds. The final exercise's rest is ignored.
- `instruction`: optional short instruction shown in the player.

The workout index is a simple list:

```json
{
  "workouts": [
    { "file": "full-body.json" },
    { "file": "stretch.json" }
  ]
}
```

## Features

- Responsive workout gallery
- Fullscreen workout player
- Timed exercises, manual repetition counting and optional automatic repetition cadence
- Exercise and rest intervals
- Pause, resume, previous and next controls
- Keyboard shortcuts: Space, Left Arrow, Right Arrow
- Installable PWA with offline caching
- GitHub Pages deployment through GitHub Actions

## Development

Open `index.html` through a local static web server. Service workers and PWA installation require HTTPS or localhost.
