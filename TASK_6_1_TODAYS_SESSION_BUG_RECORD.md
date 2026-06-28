# Task 6.1 Bug Record - Today's Session Wrong Day

## Version

- Before fix: v2.4
- After fix: v2.4.1
- Date: 28 Jun 2026

## Problem

On Sunday, the Training section's **Today's Session** card showed:

- Chest + Shoulder
- 45-60 min - Gym

This was wrong because **Chest + Shoulder is the Monday workout**. Sunday should show:

- Recovery
- 15-30 min - mobility & stretch

The Sunday chip and Sunday workout card were already correct. Only the top Today's Session card was wrong.

## Cause

The Today's Session card in `index.html` had static default HTML text:

- `todayWorkoutName` defaulted to `Chest + Shoulder`
- `todayWorkoutSub` defaulted to `45-60 min - Gym`

The existing JavaScript already had correct weekday data in `TRAINING_BY_DAY`, but `updateDashboard()` only updated the Home dashboard snapshot. It did not update the Training section's Today's Session card text.

## Fix

Updated `updateDashboard()` in `index.html` so it also writes the current day's training data into:

- `#todayWorkoutName`
- `#todayWorkoutSub`

Now the card uses the same `TRAINING_BY_DAY` source as the rest of the app.

## Files Changed

- `index.html`
- `sw.js`
- `VERSION_LOG.rdoc`
- `nutrition.html` visible version log only

## Version / Cache Update

Because `index.html` changed and the app is a PWA, the cache was bumped:

- From: `vshape-100-v2.4`
- To: `vshape-100-v2.4.1`

Version logs were updated to include `v2.4.1`.

## What To Test

1. Open `index.html` on Sunday.
2. Scroll to Training.
3. Confirm Today's Session shows `Recovery`.
4. Confirm the Sunday chip is active.
5. Confirm the Sunday workout card opens.
6. Check another weekday later to confirm the card follows that day's workout.

## Notes

No workout plan content was changed. The fix only corrected the display logic for the Today's Session card.
