# Changelog

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