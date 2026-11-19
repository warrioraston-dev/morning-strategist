# The Morning Strategist — Iteration 2

## Editorial Academy

Iteration 2 develops the existing app into a premium historical reading and strategic-learning experience. The work is deliberately incremental: GitHub Pages, Supabase publishing, the existing edition payload, local notes, bookmarks, completion records, import/export, and the original learning destinations are retained.

### Current implementation slice

- New responsive editorial visual system in `academy.css`.
- Redesigned Today page with a strong daily-edition hero, academy progress, chapter previews, and four learning pathways.
- Redesigned masterclass reader with an editorial cover, editor's briefing, chapter index, layered narrative (essential passages first, optional deeper reading expandable), strategic anatomy, short modern parallel, chronology, video links, sources, reading room, command simulation and private reflection.
- Visual command room replaces the conventional Strategy Gym quiz: readers inspect intelligence, choose an operational route or position on a schematic map, commit their orders, then receive a detailed explanation of why the choice works or fails and what the historical commander did.
- Command simulations are data-driven through `commandSimulation`, including map nodes, routes, three operational options and explanatory debriefs. The current Khwarazm campaign scenario is the first pilot.
- Existing edition fields and the legacy `sections` format remain supported.
- Edition date comparison and header date use the `Europe/Zurich` calendar.
- Existing Library, Strategic Atlas, Strategy Gym, Journal, Supabase sync, and local persistence functions are retained.

### Safety and release approach

- This branch is `iteration-2/editorial-academy`; production `main` is not changed.
- No Supabase schema, credentials, RLS policies, or publishing automation were changed.
- The app continues to use the existing public published-editions read path.
- Merge only after visual testing on Android and desktop, a Supabase sync check, and a service-worker update/offline check.

### Next implementation stages

1. Test the new Today and masterclass screens with the published Nelson edition.
2. Improve chapter progress, reading preferences, and image captions/credits while preserving the existing edition format.
3. Test the Khwarazm command simulation on Android and desktop, including each route selection and its debrief.
4. Improve Library discovery and add the first real Strategic Atlas map.
5. Validate PWA cache updates and daily edition date handling end-to-end.

### Known scope boundary

The current Atlas map is still a schematic placeholder. This release does not claim to add a georeferenced interactive map or change the daily publishing schedule. Those require separate, testable work.
