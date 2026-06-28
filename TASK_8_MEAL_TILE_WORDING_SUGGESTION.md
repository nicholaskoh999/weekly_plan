# Task 8 Meal Tile Wording Suggestion

## Current Issue

The Fuel dashboard meal tile currently shows the full meal text, for example:

> Air-fryer chicken breast + broccoli + 70 g raw rice, then prep extra chicken for office lunches.

This is accurate, but it is too long for a small dashboard tile. It wraps into multiple lines and makes the dashboard feel crowded.

## Recommended Direction

Use a short meal title in the dashboard tile, and keep the full meal details inside the Weekly Meal Plan section.

Dashboard tile should answer quickly:

- What meal window is it now?
- What should I generally eat now?
- Where can I see the full detail if needed?

## Best Option

Use short labels like this:

| Meal window | Dashboard title | Sub label | Full detail stays in Weekly Plan |
|---|---|---|---|
| Breakfast | Breakfast Plan | Breakfast · 06:00-10:30 | Actual breakfast text by weekday |
| Lunch | Lunch Plan | Lunch · 10:30-15:00 | Actual lunch text by weekday |
| Dinner | Dinner Plan | Dinner · 15:00-19:00 | Actual dinner text by weekday |
| Snack | Snack Option | Snack · 19:00 onwards | Actual snack text by weekday |

For the selected example, instead of showing:

> Air-fryer chicken breast + broccoli + 70 g raw rice, then prep extra chicken for office lunches.

use:

> Dinner Plan
> Dinner · 15:00-19:00

## Alternative Options

### Option A - Short Meal Type

- Breakfast Plan
- Lunch Plan
- Dinner Plan
- Snack Option

Pros: cleanest and fits the dashboard best.  
Cons: user needs to scroll to Weekly Plan for exact food.

### Option B - Short Food Summary

Examples:

- Chicken Rice Prep
- Economy Rice Cut
- Tuna Sandwich
- Yogurt + Fruit
- Chicken Wrap

Pros: more specific than Option A.  
Cons: needs a custom short title for every day and meal.

### Option C - Keep Full Food Text

Keep the current full meal sentence in the dashboard.

Pros: shows exact food immediately.  
Cons: too long for the tile and visually crowded.

## Recommended Implementation

Use Option A now:

- Dashboard title: `Breakfast Plan`, `Lunch Plan`, `Dinner Plan`, or `Snack Option`
- Dashboard sub label: meal window time
- Weekly Meal Plan remains the source for full details

## Suggested Future Enhancement

If more specificity is wanted later, use Option B and add a separate short-title map, while keeping full meal text unchanged in Weekly Meal Plan.

## Do Not Change

- Do not change meal choices
- Do not change quantities
- Do not change Monday-Sunday schedule
- Do not change Body Tracker logic
- Do not change weekly meal details

## My Recommendation

Change the dashboard tile to short meal window labels. For the current selected tile, use:

> Dinner Plan
> Dinner · 15:00-19:00

This keeps the dashboard clean while preserving the full meal detail below.
