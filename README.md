# Flint Exercise Media

Exercise demo clips for the Flint fitness app.

## Two ways the clips are served

### 1. Release assets (what the app consumes)

The app lazy-loads one clip per exercise from the **`v1` release**, using a flat,
slugified filename:

- Pattern: `releases/download/v1/<slug>.mp4`
- 350 clips, one per exercise in the app's library (migration `0007`)
- For exercises that have both a women's and a men's demo, the men's clip is used.

Example: `releases/download/v1/barbell-curl.mp4`

### 2. Full source tree (this repo)

The complete library of **653 clips** is committed here for browsing, archival,
and future per-gender selection, preserving the original layout:

```
<gender>/<muscle group>/<Exercise Name>.mp4
```

- `gender` — `girl` or `men`
- 339 `girl` clips, 314 `men` clips

These are reachable as raw URLs (path segments must be URL-encoded), e.g.:
`https://raw.githubusercontent.com/shaantanu9/flint-exercise-media/main/men/biceps/Barbell%20Curl.mp4`

## Manifest

`exercise_video_manifest.csv` maps every clip to its gender, muscle group,
exercise name, relative path, and byte size.
