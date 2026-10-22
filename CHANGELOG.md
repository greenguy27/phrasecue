# Changelog

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
