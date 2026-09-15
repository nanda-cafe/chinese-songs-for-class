# 中文歌词 · Chinese Lyrics for Class

A small collection of annotated Chinese song lyrics built for my Chinese class.

Each song is a single self-contained HTML page. Every character is tagged with
its HSK level, part of speech, pinyin, and a literal gloss. Toggle any of those
layers on or off to study the way that suits you — or hit **Karaoke** to strip
everything back to just Hanzi and pinyin and follow along in time with the
recording.

---

## Why I built this

Textbook dialogues are fine, but they don't stick. Songs do.

The problem is that most lyrics you find online give you *either* the characters,
*or* the pinyin, *or* a loose translation — never all three, and never with any
sense of which words are actually worth learning at your level. So I started
building these pages by hand: one character at a time, with HSK colours, grammar
tags, and a literal gloss above each word, plus a poetic translation underneath.

The result is something I can use in three different ways depending on how much
help I need on a given day.

---

## What's in a song page

### Annotations (all toggleable)

| Layer | What it shows | Toggle |
|---|---|---|
| **HSK colours** | Underline colour = HSK 1–6 difficulty | 📊 |
| **Grammar tags** | Part of speech under each word | 📖 |
| **Literal gloss** | Small translation above each Hanzi | 🌐 |
| **Pinyin** | Romanisation with tone marks | 🔤 |
| **Sentence translation** | Poetic English / Portuguese line below | 🌐 |
| **Dictionary link** | Every Hanzi links to its MDBG entry | — |

Toggle **Translation** off and both the literal gloss *and* the sentence
translation disappear — useful when you want to test yourself against the
Hanzi alone. Toggle **Pinyin** off and the romanisation goes too, which is
where things get genuinely difficult.

### Karaoke mode 🎤

Toggling Karaoke on automatically hides every annotation except Hanzi and
pinyin, then highlights the lyrics line-by-line and character-by-character in
time with the recording.

When a song has instrumental gaps — an intro, a bridge, a fade-out — an
instrumental marker appears in place of the lyrics so the display never looks
frozen:

♪ 前奏 · Intro
♪ 间奏 · Instrumental
♪ 尾声 · Outro

Karaoke mode has its own sticky control bar with:

- **▶ Start** — begins playback at the first character
- **⟲ Reset** — back to the top
- **Progress bar** — click anywhere to seek
- **±0.5 s nudge** — fine-tune sync against your specific recording
- **Space bar** — play / pause

When you toggle Karaoke off, every annotation toggle you had set before is
restored exactly as it was.

---

## Songs available

| Song | Artist | Year |
|---|---|---|
| [月亮代表我的心](yue-liang.md) | 邓丽君 · Teresa Teng | 1977 |

More being added as the class moves along.

---

## How to use it

### Just reading / studying

Open any song page in a browser. Everything works offline — no build step, no
dependencies, no server. The whole page is a single `.html` file.

### If you're deploying your own copy

1. Fork or clone this repository.
2. Add your song as `index.html` (or any filename you like) at the root.
3. In GitHub: **Settings → Pages → Source: Deploy from a branch → `main` / `(root)`**.
4. Wait a minute or two. Your site will be at:
   `https://<your-username>.github.io/<your-repo>/`

---

## How the annotation system works

Every word in every song is a small data object:

```js
{
  hz: '月亮',        // Hanzi
  py: 'yuè liang',   // Pinyin with tone marks
  gloss: 'moon',     // Literal gloss (shown above the character)
  hsk: 3,            // HSK level → underline colour
  pos: 'noun',       // Part of speech → glossary link
  posName: 'n.'
}
