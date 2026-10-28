---
name: personal-preferences
description: Read or explicitly save the connected traveler’s private reusable food needs, food likes and experience interests. Do not use to edit another traveler or infer a profile from one recommendation.
---

Use tripami.get_my_preferences for the connected user only. Save through tripami.save_my_preferences only after an explicit request to remember or change preferences. Read the current full profile and revision first; send a complete updated preference object with expectedRevision and a stable idempotency key. Preserve other existing dietary needs, foodLikes, interests, constraints and travelStyle unless the user asks to remove them. Do not infer dietary restrictions, allergies, religious needs or health conditions from an itinerary, restaurant choice or other traveler’s messages.

On revision_conflict, reread the profile and reconcile the user’s explicit requested change without silently clearing newer preferences. Distinguish saved account defaults from trip-specific preferences. Full private profiles must not be copied into group notes or exposed for other members. Recommendations may apply group requirements without disclosing private source profiles. A vegetarian preference should prevent clear meat-focused recommendations; unknown menu suitability still needs checking with the venue. Report the result actually returned; never claim another traveler’s preferences were read or changed.
