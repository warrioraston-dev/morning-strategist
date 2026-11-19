# The Morning Strategist — Iteration 2

## Editorial Academy

Iteration 2 develops the existing app into a premium historical reading and strategic-learning experience. The work is deliberately incremental: GitHub Pages, Supabase publishing, the existing edition payload, local notes, bookmarks, completion records, import/export, and the original learning destinations are retained.

### Current implementation slice

- New responsive editorial visual system in `academy.css`.
- Redesigned Today page with a strong daily-edition hero, academy progress, chapter previews, and four learning pathways.
- Redesigned masterclass reader with an editorial cover, editor's briefing, chapter index, long-form chapter presentation, strategic anatomy, short modern parallel, chronology, video links, sources, reading room, challenge entry point, and private reflection.
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
3. Upgrade Strategy Gym feedback and historical decision framing.
4. Improve Library discovery and add the first real Strategic Atlas map.
5. Validate PWA cache updates and daily edition date handling end-to-end.

### Known scope boundary

The current Atlas map is still a schematic placeholder. This release does not claim to add a georeferenced interactive map or change the daily publishing schedule. Those require separate, testable work.
