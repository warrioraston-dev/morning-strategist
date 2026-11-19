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
- Library search now indexes titles, themes, summaries and chapter headings; edition cards are safely rendered and show last-read progress.
- Reader adds automatic chapter progress, a resume point on Today, adjustable text size and reading width, and a persistent expand/collapse control for deeper passages.
- Recent published editions are cached locally for offline reading; Supabase remains the live source when online. Service worker cache is versioned and static assets use network-first with offline fallback.
- Backup/restore now preserves notes, bookmarks, completion, reading progress and reader preferences as well as edition content.
- PWA installation has a visible install action with Android manual-install guidance when the browser does not provide its native prompt.
- Strategic Atlas now contains two interactive theatre tabs: the Khwarazm campaign and Trafalgar, with explanatory operational diagrams explicitly labelled schematic and not to scale.
- Strategy Gym includes command simulations for both the current Khwarazm edition and the legacy Nelson edition; future editions are instructed to publish their own `commandSimulation` data.
- Existing Library, Strategic Atlas, Strategy Gym, Journal, Supabase sync, and local persistence functions are retained.

### Safety and release approach

- This branch is `iteration-2/editorial-academy`; production `main` is not changed.
- No Supabase schema, credentials, RLS policies, or publishing automation were changed.
- The app continues to use the existing public published-editions read path.
- Merge only after visual testing on Android and desktop, a Supabase sync check, and a service-worker update/offline check.

### Release-candidate verification still required

1. Test the Today page, layered reader, reader controls and resume position on Android and desktop.
2. Exercise all three choices in both the Khwarazm and Trafalgar command rooms and inspect the debriefs.
3. Confirm live Supabase sync and offline fallback on a real device.
4. Confirm Android installation from Chrome and service-worker update behavior.
5. Verify the next scheduled edition at 07:00 Europe/Zurich and confirm its correct edition date and `commandSimulation` payload.

### Known scope boundary

The Atlas and command-room diagrams are explanatory schematics, not georeferenced navigation charts or exact unit-by-unit reconstructions. Notes, bookmarks, completion and reading progress are stored on the device; the cloud currently supplies published editions only. No Supabase schema, RLS, credentials, or publication schedule changes are part of this release candidate. Production `main` remains untouched until the user explicitly approves release.
