# Changelog

## [1.0.3] - 2026-09-09

### Added
- Direct puzzle submission functionality in the Student Dashboard, allowing students to select a submission date and submit completed puzzles [1, 2].
- Dynamic "Submitted on [date]" badges with edit controls in the Student View, keeping completed puzzles visible rather than hiding them [2, 3].

### Changed
- Refactored `updateRecordDate()` and added `submitStudentPuzzle()` to instantly sync student-entered submission dates with both the Teacher Mode matrix and Supabase [4].

## [1.0.2] - 2026-09-09

### Added
- Replaced the student selection dropdown with an interactive typed search input in the Student Dashboard, featuring real-time filtering, auto-selection on single match, choice buttons on multiple matches, and spelling verification prompts.

### Changed
- Simplified accordion group section headers across both Teacher and Student views by removing the "🌐 Source:" and "🌐" text prefixes for a cleaner interface.

### Fixed
- Fixed a global variable collision (`supabase` vs. `window.supabase`) by renaming the client to `supabaseClient` and adding safe initialization wrappers to prevent page crashes when CDN libraries are blocked.
- Fixed a rendering bug where matching a student search query displayed "undefined" by properly destructuring filtered result objects.
- Added a safety check in `saveData()` to prevent an uninitialized empty dataset from accidentally overwriting live cloud database records in Supabase.

## [1.0.1] - 2026-08-20
### Fixed
- Fixed a global variable naming collision (`supabase` vs. the CDN-provided `window.supabase`) that threw a `SyntaxError` on page load, silently aborting the entire script. This was breaking the "Switch View" and "Forgot Password?" buttons, and preventing any data from loading or saving. The client variable was renamed to `supabaseClient` throughout.

## [1.0.0] - 2026-08-20
### Added
- Initial official release of the application.
- Core logic puzzle tracking layout and responsive design.
- Ability to manage a student roster with individual student views.
- Two-step print request verification flow for students to check physical folder resources first.
- Students able to view a list of puzzles still available for completion to avoid repeat submissions.
- Secure, password-protected Teacher Mode with password reset request capability.
- Teacher dashboard for managing puzzle inventory (add, edit, duplicate, delete, and toggle visibility).
- Interactive teacher matrix to quickly filter and record puzzle submission dates for students.
- Streamlined teacher queue to track and mark student print requests as fulfilled.
- Local database backup capabilities via JSON file export and pure-override restore.