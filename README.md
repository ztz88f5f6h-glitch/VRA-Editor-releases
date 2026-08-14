# VRA-Editor

VRA-Editor is a desktop application for creating and editing **VRA Core 4**
metadata records — the standard used across museums, galleries, libraries,
and archives to describe works of art, images, and collections. It's built
for the people who actually do this work — catalogers, archivists,
curators, and researchers — not for an IT department.

## No server, no database, no infrastructure required

Most cataloguing software assumes an institution with a server, a database
administrator, and a reliable network behind it. VRA-Editor doesn't. It
works entirely off plain XML files sitting in ordinary folders — on your
own computer, on a shared network drive, or nowhere but a laptop.

That matters because a lot of humanities and arts work doesn't happen
inside a well-resourced institution: a small historical society with no IT
staff, a researcher cataloguing a private collection, a curator documenting
an exhibition on-site, a conservator working in storage with no wifi.
VRA-Editor is built so none of that gets in the way:

- **Works with no network at all.** Stage a local copy of your records
  before you lose connectivity — a field trip, a site visit, anywhere
  without a signal — and keep cataloguing exactly as normal. When you're
  back online, reconcile your offline changes back into the shared
  archive; anything that also changed on the other side while you were
  away is flagged for you to resolve by hand, never silently overwritten.
  Staging only ever copies the *Edit* folder — records actively being
  worked on, typically a modest, everyday-sized transfer — not the whole
  archive; the reviewed/approved collection behind it, which can grow
  very large over the life of a project, is never touched.
- **Your data is just files.** Every record is a plain XML file, in a
  folder you control. Back it up, sync it, move it, put it under whatever
  storage you already use — nothing is locked inside a proprietary
  database.
- **Scales to whoever's actually using it.** One person on one laptop
  works the same way as a small team sharing a folder on a network drive.
  There's nothing to install or administer either way.

## What it does

- **Guided, form-based editing.** A Simple view organizes a record by
  section — Titles, People, Dates, Measurements, and so on — so you don't
  need to know the underlying schema by heart. Fields governed by a fixed
  set of allowed values (a title's type, a relationship's type) are
  presented as dropdowns built directly from the schema, not free text, so
  those can't be entered incorrectly in the first place.
- **Validation against the official VRA Core 4 schema.** You can save
  incomplete work in progress at any point, but nothing moves into review
  until it's genuinely schema-valid — checked automatically, with a
  plain-English explanation of what's missing if it isn't, not a raw
  parser error.
- **A full audit trail and version rollback**, backed by an ordinary Git
  repository the app manages for you behind the scenes. Every saved change
  is there to review, and any past version of a record can be restored
  into a new file — no Git knowledge required to use it.
- **Controlled-vocabulary search across a wide range of authorities** —
  VIAF, the Getty vocabularies (AAT, TGN, ULAN), the NGA's GEOnet Names
  Server, and the Library of Congress vocabularies (LCSH, LCNAF, LCGFT,
  LCTGM) — searched directly from the relevant field, with results cached
  locally so a repeated or related search doesn't need the network again.
- **Media linking with EXIF/IPTC round-tripping**, for image records: link
  an image file and the app reads its dimensions, GPS position, and
  capture date straight into the record, and can write the record's own
  title, description, people, rights, and subjects back into the file's
  own metadata.
- **A configurable, folder-based review workflow** — edit, submit, review,
  approve, or reject, each its own folder, freely reassignable in Settings
  to wherever your archive actually lives.

## What's new

- **v1.1.0** — A dedicated app icon, replacing the placeholder company
  logo. Sync Media now asks whether to use the file with a matching
  name or browse for a different one, instead of silently guessing;
  Browse now starts in the record's own folder. Import now surfaces
  media files that don't match any record, letting you stash them into
  `done/` or dismiss them instead of leaving them stuck in `ingest`
  indefinitely.
- **v1.0.0** — Initial release.

---

See [`user_manual.pdf`](user_manual.pdf) in this repo for the full user
manual, or **Help** inside the app itself.

## Getting the app

This repo holds no source code — it exists only so built distributions can
be downloaded without needing access to the private source repository. Grab
the macOS `.app`, the Windows installer, or the Linux `.deb` from the
[Releases](../../releases) page.
