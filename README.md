# 🎤 PhraseCue

**A free, private lyric prompter for singers, built around vocal-phrasing notes.**

Load your song's full mix, its instrumental and your lyrics. Tap once through the song to time it, then sing along to the instrumental while each line lights up on cue. Stress marks, pitch arrows, breath marks and performance notes are all shown in place.

![PhraseCue screenshot](docs/screenshot.png)

**▶ Try it:** https://greenguy27.github.io/phrasecue/

---

## Why PhraseCue

- **Runs anywhere.** It's a single HTML file that works in Chrome, Edge, Safari or Firefox on Windows, macOS or Linux. There's nothing to install and no internet connection needed.
- **Private.** Your audio and lyrics never leave your computer. There are no accounts, uploads, ads or tracking.
- **Phrasing-aware.** Shows **BOLD** stress, `→ ↗ ↘` pitch arrows, `//` breath marks and *(performance directions)* from your phrasing notes, not just plain lyrics.
- **Switch tracks mid-song.** Flip between the full mix and the instrumental mid-song without stopping, so you can listen to a phrase and then sing it.
- **Simple timing.** Tap **Space** at the start of each line. Mistakes are easy to undo or nudge.
- **Portable.** Timing saves as a small `.timing.json` file, or exports as a standard `.lrc` that other karaoke apps can read.
- **Practice tools.** Loop a line, a section or your own A–B range, and slow down to 50% without changing pitch.
- **Timeline.** See the vocal and every line's start under the lyrics. Drag a marker to retime a line, scroll to zoom.
- **Snap (auto-timing assist).** With both mixes loaded, PhraseCue isolates the lead vocal (full mix minus instrumental) and nudges your taps onto the real vocal starts.
- **Record yourself.** Sing over the instrumental, play the take back in sync, and download your voice or a voice-plus-instrumental WAV.

## Quick start

1. Open `index.html` in your browser by double-clicking it, or use the hosted link above.
2. Drag in your files all at once:
   - the **full mix** audio (MP3, WAV, M4A, OGG, FLAC)
   - the **instrumental**. If its name contains *karaoke*, *instrumental*, *without*, *backing*, *minus* or *no vocal*, it's detected automatically. Otherwise PhraseCue asks which file has no vocals.
   - one or more **lyrics** files (`.txt`, `.md` or `.lrc`)
3. **Time it, once per lyrics file:** press **S**, then **Space** to start the song, then tap **Space** the moment the singer starts each **blue** line. With both mixes loaded, **🧲 Snap** tightens your taps automatically.
4. **Sing:** press **S** to leave timing mode, **V** for the instrumental, then **Space** to play.
5. **Keep it:** use **Timing ▾ → 💾 Save timing file** and keep the `.timing.json` file next to your song. Next time, or on another computer, drag it in with the other files.

Want to see the lyric formats? Load the files in [`examples/`](examples/) along with any audio file.

## Lyric file formats

### Plain lyrics
```
Song Title

(Verse 1)
First line of the verse
Second line of the verse

(Chorus)
...
```
The first line is the title. Lines in `( )` or `[ ]` are section headers, and every other line is a lyric line.

### Vocal-phrasing guide (Markdown-style)
```
# SONG TITLE
*Genre · Voice · ~84 BPM*

## [VERSE 1]
*(Soft and close to the mic.)*

→ We folded **PA-per** / ↘ on the kitchen floor,
→ wrote our names / on the **SAILS——** ↘

//
```
| Markup | Shown as |
|---|---|
| `# Title` | Song title (first heading) |
| `## [SECTION]` | Section header |
| `*(direction)*` | Performance note in italics |
| `**WORD**` | Stressed word, highlighted |
| `//` | Breath mark |
| `---` | Ignored (spacing only) |
| Any other line | Lyric line that gets timed |

### Suno-style lyrics
```
[Style: Dark Americana, Blues Rock]
[Verse 1]
[Male vocal, low and close]
First line of the verse
Second line (echo)

[Instrumental Break]

[Chorus]
...
```
PhraseCue reads these the way they're written for Suno:
- **Sections:** `[Verse 1]`, `[Chorus]`, `[Bridge]` and so on become section headers.
- **Breaks:** `[Instrumental Break]` or `[Guitar Solo]` with no lyrics under it names the instrumental break.
- **Directions:** tags like `[Male vocal, soft]` show as performance notes, and a combined tag like `[Chorus, both vocals]` gives a header plus a note.
- **Style lines:** `[Style: …]` shows as a small line under the title.
- **Backing lines:** a whole line in `( )` shows smaller and isn't timed. A `(word)` inside a lyric line is shown dimmer.
- **Title:** a short first line followed by a blank line becomes the title. If there isn't one, the file name is used.

### Duets / parts
Lines are colored by singer. A small color key appears under the title, the timeline markers match, and exported videos show the singer's name whenever it changes. The part is set by:
- **Directions:** `[Male vocal]`, `[Female vocal]`, `[Both vocals]` (also *duet*, *choir*, *together*), in any lyrics format
- **Named parts:** `[Part: Lila]`, or a bracket tag that's just a name, like `[Elyra]`
- **Line prefix:** `Wren: I left the light on…`. The name is removed from the sung text.

A part lasts until the next one is set. Songs with only one singer aren't colored.

**Duet layout:** by default, the first singer's lines sit on the **left**, the second singer's on the **right**, and **Both** lines are centered, in the app and in exported videos. Switch it with **Timing ▾ → 👥 Duet layout** (app) or **Duet layout** in the video panel.

**Singer names in videos:** the video panel can show the singer's name **above every line** (good for vertical TikTok, Shorts and Reels), **only when the singer changes**, or not at all. Names come from the singer tags, so they're never counted as lyric lines and never need timing.

### LRC
Standard `[mm:ss.xx] lyric` files load already timed.

## Instrumental breaks

During an instrumental break, the last line dims and a **♪ Instrumental** bar counts down to the next line.
- **Estimated breaks:** when the gap before the next line is much longer than your usual line length, PhraseCue treats the rest of it as a break, marked *estimated*. You can turn this off with **Timing ▾ → ♪ Estimate breaks**.
- **Exact breaks:** while timing, press `Enter` the moment the singing stops, then keep tapping `Space` when it comes back. `Backspace` undoes the mark, `Shift`+`Enter` removes it, and on the timeline you can drag the blue break marker.
- A section in your phrasing file with no lyric lines, like `## [SHORT INSTRUMENTAL]`, gives the break its name.
- Breaks are saved in the timing file, and exported to `.lrc` as an empty timestamp, which is the standard way to show "no lyrics here".

## Pasting and editing lyrics

**📝 Lyrics** (or *paste / type your lyrics* on the welcome screen) opens a text box. Paste or type lyrics in any supported format, give them a name, and click **Use these lyrics** (`Ctrl`+`Enter`).
- Pasted lyrics are saved in your browser and show up in the lyrics menu next time. **⬇ Download .txt** saves a file copy.
- Opening the box again edits the current lyrics. **Edits keep your timing**: lines are matched by their text, so fixed typos, added lines and removed lines only affect the lines you touched. New lines just need tapping.
- **No MP3 yet?** You can still paste and read lyrics. Choose **Continue without audio** on the welcome screen, or just click **Use these lyrics**, then step through the lines with `↑` / `↓` or by clicking them. Load the MP3s whenever they're ready to time the song.
- If you load a lyrics *file* with the same name, the file's text is used, with your timing carried over the same way.

## Lyric & karaoke videos

**🎬 Video** turns the timed lyrics into a video file, with no other software needed.
- **Audio:** full mix (lyric video) or instrumental (karaoke video).
- **Shape:** landscape 1920×1080 (YouTube), vertical 1080×1920 (Shorts, Reels, TikTok) or square 1080×1080.
- **Range:** the whole song, or just the current loop. That's handy for a chorus teaser: loop the chorus with `Shift`+`L`, then export.
- **Look:** an optional background image (your cover art works well) with a darkness slider, a title card with your credit line, section labels, ♪ instrumental breaks, and an option to hide phrasing marks for a clean public video.
- **"Made with PhraseCue" tag:** a small see-through tag in the corner, plus a line on the end card. It's on by default; untick it in the video panel to turn it off.
- **Format:** MP4 (H.264) when your browser can record it, otherwise WebM. The panel shows which before you record. YouTube accepts both. For Instagram and TikTok, convert WebM to MP4 with a free tool such as HandBrake.
- **It records in real time,** so a 4-minute song takes 4 minutes. Keep the tab open and visible while it records.

## Practice tools

- **Loop:** `L` loops the current line, `Shift`+`L` loops the current section, and `A` / `B` set your own start and end. Press `L` again or click the gold loop button to stop.
- **Speed:** the *Speed* menu (or `,` and `.`) plays at 50–110%. Pitch stays the same.
- **Timeline:** the strip above the controls. Gold markers are your lines and blue ticks are detected vocal starts. Click to jump, drag a marker to retime it (hold `Shift` to skip snapping), scroll to zoom, drag to pan, and double-click to zoom back out.
- **Snap:** turned on automatically when both mixes are loaded. Taps land on the nearest strong vocal start. It isn't perfect: if a stamp looks wrong, drag its marker or turn Snap off. It doesn't time the whole song by itself, because word onsets inside a line look just like line starts.
- **Record:** press `R` to start and stop. Recording starts from where you are, or from the loop start, and stops at the loop end. **Wear headphones.** Open **🎙 Takes** (`T`) to play takes back, adjust *Voice timing* if you sound early or late, and download **Voice** (webm/m4a) or **Mix** (WAV, takes recorded at 100% speed). Takes aren't saved after you close the tab.
  - The browser asks for microphone access the first time. Recording works from the hosted link in every browser. Opening the file directly works in Chrome and Edge, but Safari may refuse.
  - Chrome asks once to *allow multiple downloads* the second time you download from the page. Click Allow.

## Keyboard shortcuts

| Key | Action |
|---|---|
| `Space` | Play / pause (in timing mode: stamp the blue line) |
| `P` | Play / pause in any mode |
| `S` | Timing (sync) mode on/off |
| `V` | Full mix ↔ instrumental |
| `←` `→` | Seek 5 seconds |
| `↑` `↓` | Previous / next line |
| `[` `]` | Move the current line 0.1 s earlier / later |
| `Shift` + `[` `]` | Move **all** lines 0.1 s earlier / later |
| `Backspace` | Timing mode: undo the last stamp (or break mark) |
| `Enter` / `Shift`+`Enter` | Mark / remove an instrumental break after the current line |
| `+` `−` | Text size |
| `F` | Full screen |
| `Home` (Mac: `Fn`+`←`) | Back to the start |
| `L` / `Shift`+`L` | Loop current line / section (again = stop) |
| `A` `B` | Set loop start / end |
| `,` `.` | Slower / faster |
| `R` | Record / stop |
| `T` | Show takes |
| `?` | Help |

Click any line to jump to it. The **Read-ahead** slider lights each line up a moment early so you can see what's coming.

## Tips

- **Lines feel late?** Raise *Read-ahead*, or press `Shift`+`[` a few times.
- **Off by a whole line?** You probably tapped at the *end* of each line. Use **Timing ▾ → 🗑 Clear timing** and tap at the *start* of each blue line. The timeline makes this easy to spot: gold markers should sit at the left edge of each vocal phrase.
- Timings are tied to the lyrics file's name and line count. Fixing a typo is fine, but adding or removing a line means retiming from that point. In timing mode, click the line and keep tapping.

## Putting it on your own website

- **Link to it:** turn on GitHub Pages for this repo (Settings → Pages → Deploy from branch → `main` / root) and link to `https://greenguy27.github.io/phrasecue/` (already live for this repo).
- **Self-host:** upload `index.html` to any web host. It's fully self-contained.
- **Embed:** `<iframe src="https://greenguy27.github.io/phrasecue/" style="width:100%;height:85vh;border:0" allow="fullscreen"></iframe>`. Some site builders limit iframes, so a link or button is the most reliable option.

## Privacy

PhraseCue makes no network requests. Files you load and anything you record are processed locally by your browser. Timings are stored in your browser's local storage and in any files you choose to download. Clearing your browser data erases the browser copy, so keep your `.timing.json` files.

## License

[MIT](LICENSE) © 2026 Chris Ross · [CRBooks.ink](https://crbooks.ink)

The sample song in `examples/` was written for this project and may be used freely along with the code.
