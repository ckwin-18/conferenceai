# ConferenceAI v7 — Local capture, export and restore

## Capture
1. Open `index.html` in a modern browser or deploy the folder to HTTPS hosting.
2. Create a conference, then add sessions as you attend them.
3. Add notes, photos, voice recordings and uploaded files. Long recordings are better made with iPhone Voice Memos and then uploaded.
4. Records are saved in IndexedDB on the *current device/browser/origin*, not in the app folder or a cloud service.

## Backup and restore
- **Backup all** (top right): lossless, restorable ZIP of every conference, session and original attachment.
- **Backup conference** (inside a conference): lossless, restorable ZIP of that conference and its sessions.
- **Restore** (top right): imports a ConferenceAI **v7** backup ZIP; records with matching IDs are replaced, other records remain. ZIPs exported for AI are not restorable, and older v6 backup ZIPs do not include the necessary v7 metadata.
- Test a restore on a different browser/profile before relying on it.

## Export for AI
Inside a conference, select photo quality and click **Export for AI**. The ZIP contains event/session JSON, `notes.md`, and session folders `photos/`, `recordings/` and `uploads/`, plus a `manifest.json` for traceability. AI-ready export does not create transcripts or summaries itself. Upload the archive or extracted files to ChatGPT subject to ChatGPT's upload limits. For long audio, transcripts may be needed separately.

Photo choices: original files; optimised (max 2560px, JPEG approximately 85% for images that need conversion); compact (max 1600px, JPEG approximately 75%). Only exported copies change. Unsupported photo formats remain as originals. Resizing can strip photo metadata.

## Limits and safety
- ZIP creation and restore read large media into memory; test small exports first. Huge audio/photo collections may exceed browser/device memory or ZIP limits, especially on iPhone.
- Exports use uncompressed ZIP entries for compatibility and integrity checking. JPG/M4A are already compressed.
- IndexedDB may be cleared by browser settings or storage eviction. Back up frequently.
- No cloud sync, transcription, search/Q&A or automatic report generation are implemented in v7.
- Recording requires permission and may stop when the phone sleeps; prefer native Voice Memos for long talks.
