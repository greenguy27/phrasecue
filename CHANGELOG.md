# Changelog

## 1.5.1 (in testing)
- **Lyrics editor tag buttons, complete and grouped** (Sections · Breaks · Voices · Marks): adds [Intro], [Final Chorus], [Post-Chorus], [Hook], [Interlude], [Guitar Solo], [Breakdown], [Part: name], [Style: …] and ( backing )
- **Smart numbering:** [Verse #] inserts the next verse number; [Pre-Chorus] numbers from the second one
- **Vocal tags ready for detail:** [Male vocal, …] puts the cursor inside so you can type "low and intimate"
- **Reader fix:** tags like [Short Instrumental] or [Soft Guitar Solo] now count as breaks, not notes; empty details like "[Male vocal, ]" are tidied

## 1.5.0 (2026-10-25)
- **Cover art & tinted stage:** add a cover image per song (click the cover, ⋯ → Cover art, or drop an image); the lyrics stage takes on its colors
- **Song panel:** cover, title, details and singer key beside the lyrics on wide screens
- **Lyric view:** current line larger, past lines softly blurred, singer names above each change of singer; round play button with elapsed / total time
- **Lyrics editor:** separate Song title and Version fields; one-click tags ([Verse], [Chorus], [Instrumental Break], [Male/Female/Both vocal], // breath, **stress**); live counts and a "timing kept" preview
- **Share a line:** turn any line into a 1080×1080 or 1080×1920 PNG card with the song's cover or a moonlit background, glow color, credit line and editable text
- **Poster video style:** bold solid-color backgrounds with heavy type for vertical videos (six colors)
- **Clearer controls:** 🎤 Sing | ⏱ Time and Vocals | Karaoke switches replace the toggle buttons, so the current state is always visible
- **Tidier top bar:** one row; loaded files, text size, full screen, undo, help and About moved into a **⋯** menu
- **Undo:** pop-up with Undo (and `Ctrl+Z`) for clearing timing, moving lines, timeline drags, removing break marks and lyrics edits; no more "are you sure?" dialog
- **Welcome checklist:** live ✓ for Lyrics, Full mix, Instrumental (optional) and Timed, showing exactly what's missing

## 1.4.0 (2026-10-23)
- **Lyrics-only mode:** read and step through lyrics before the MP3 exists ("Continue without audio"); playback, timing and video wait for audio
- **Duet layout:** singer A left, singer B right, both centered (app + videos, switchable); video option to show singer names above every line, on change, or off (names are labels, never timed)
- **Asks which MP3 is the karaoke version** when the file names don't say (no more silent guessing)
- **📝 Paste / edit lyrics:** type or paste lyrics in any format, saved in the browser, Download .txt, `Ctrl+Enter` to use
- **Timing survives edits:** lines are matched by text, so only new or changed lines need re-tapping (timing files now include line text; older timing files still load)
- **Duet / part colors:** `[Male vocal]` / `[Female vocal]` / `[Both vocals]` / `[Part: Name]` / `Name:` prefixes color lines by singer, with a key, colored timeline markers, and singer labels in exported videos
- **Suno-style lyrics:** `[Verse]` / `[Chorus]` sections, `[Instrumental Break]` named breaks, `[Male vocal, …]` performance notes, `[Style: …]` meta line, `( )` backing lines (untimed) and inline `(echo)` dimmed

## 1.3.1 (2026-10-21)
- Welcome screen byline now shows the GitHub name (greenguy27, linked to the GitHub profile) · CRBooks.ink

## 1.3.0 (2026-10-21)
- New welcome screen: app name and logo, "by Chris Ross · CRBooks.ink", version, what it does, 3 quick steps, privacy note, links to help, About and source
- Optional "Made with PhraseCue" tag on exported videos: small corner tag + end-card line; on by default, untick to remove (remembered)

## 1.2.0 (2026-10-21)
- **🎬 Video export:** lyric or karaoke videos, landscape / vertical / square; whole song or current loop; background image, title card, credit line, optional clean (no phrasing marks) style; MP4 (H.264) when supported, otherwise WebM

## 1.1.0 (2026-10-21)
- **Practice:** loop a line (`L`), a section (`Shift+L`) or an A–B range; speed 50–110% with pitch preserved (`,` `.`)
- **Timeline:** vocal envelope, line markers and section labels; click to seek, drag markers to retime, scroll to zoom
- **Snap:** isolates the lead vocal (full mix − instrumental), detects phrase starts and snaps taps/drags to them
- **Record yourself:** mic recording over the instrumental, takes list, synced playback, voice-timing offset, voice or WAV-mix download
- **Instrumental breaks:** "♪ Instrumental" banner with countdown bar; estimated from long gaps, or marked exactly with `Enter` while timing (draggable on the timeline, saved in timing files and LRC)
- Timing actions moved into a **Timing ▾** menu; help and README updated

## 1.0.0 (2026-10-21)
First public release.
- Single-file lyric prompter: plain, vocal-phrasing (Markdown-style) and LRC lyrics
- Tap-to-time sync mode with undo, double-tap protection and per-line/global nudging
- Seamless full-mix ↔ instrumental switching
- Read-ahead, countdowns before entries and after long breaks, progress bar per line
- Timing saved in the browser, as `.timing.json`, or exported as `.lrc`
- About screen; no network requests, no tracking
