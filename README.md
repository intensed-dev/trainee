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
    },
    {
      "name": "Dumbbell Curls",
      "instruction": "Lift and lower the weights in a controlled rhythm.",
      "type": "reps",
      "reps": 12,
      "secondsPerRep": 3,
      "rest": 20
    }
  ]
}
```

- `id`: unique identifier for the workout.
- `name`: title shown in the workout gallery.
- `description`: optional description for future use.
- `icon`: optional Lucide icon key.
- `exercises`: ordered list of workout steps.
- `duration`: exercise duration in seconds (for timed exercises).
- `rest`: rest after this exercise in seconds. The final exercise's rest is ignored.
- `type`: set to `"reps"` for a repetition-based exercise. Leave it out for a timed exercise.
- `reps`: target repetition count for `type: "reps"`.
- `secondsPerRep`: optional automatic cadence in seconds per repetition. When omitted, each repetition is counted manually with the large button in the player.
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
- Exercise and rest intervals
- Repetition exercises with manual counting or automatic cadence
- Pause, resume, previous and next controls
- Keyboard shortcuts: Space, Left Arrow, Right Arrow
- Installable PWA with offline caching
- GitHub Pages deployment through GitHub Actions

## Development

Open `index.html` through a local static web server. Service workers and PWA installation require HTTPS or localhost.
