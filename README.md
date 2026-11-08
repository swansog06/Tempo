# Tempo

**A fitness and nutrition tracker that adapts to how you train.**

Tempo combines food logging and training plans in one app, built to be installed to an iPhone home screen as a web app. Dark mode, one sage accent, no clutter: no water tracking and no motivational pop-ups.

**Live demo:** https://greys-tempo-app.netlify.app

## Features

### Food
- Searchable database of **~420,000 branded foods**, cleaned from the USDA branded-foods dataset
- Results show the common name first, then brand · serving, then calories and protein/carbs/fat
- MyFitnessPal-style serving sizes, favorites, saved meal combos and a recipe builder
- Create your own foods, with a warning (never a block) when the macros don't add up to the calories
- Daily summary and fuel tips based on that day's training

### Training
- Pick a goal (muscle, fat loss, hybrid, endurance, mileage and more) and get a suggested plan
- Swap or remove any session or exercise, or build your own program
- Lifts are planned by sets and reps (default: a warm-up per muscle group, then 2×6–8)
- Runs show pace and heart-rate targets; interval sessions show reps, distance, time per rep, pace and HR
- Tap any day to see what you did or what's coming up

### Progress
- Overview cards for Body, Nutrition and Running that open into detailed views
- Running stats only appear for people who run

### Everything else
- Units default to lb and cal, with a setting to switch
- Installs to the home screen and works like an app
- Your data stays on your device, with export/import backups

## How it works

Tempo is a single-page web app written in plain JavaScript, with no framework, no build step and no server:

```
index.html        page shell
app.js            app logic: food search, training plans, progress, storage
style.css         styles
s/manifest.json   index of the food-database shards
s/i*.json         search index shards
s/r*.json         food record shards
```

The food database is split into ~470 small JSON files so the app only downloads the pieces a search needs, keeping it fast on a phone.

## Run it locally

Any static file server works:

```bash
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Roadmap

- Barcode scanning
- AI recipe maker
- AI training tools
- Apple Watch and Garmin data import (pace and heart rate)
- Native iPhone app

## Data source

Food data is derived from the USDA FoodData Central branded foods dataset (public domain).
