# showcase

One page for the things I build with AI. No server, no build step, no
dependencies: it is `index.html` and a folder of screenshots.

## Adding an entry

Open `index.html`. The first thing in the file is a list called `WORK`.
Add an object to it:

```js
{
  title: "FRIDAY",
  kicker: "voice assistant",
  blurb: "Runs entirely on my own hardware. The hard part was ...",
  tags: ["local llm", "voice"],
  date: "2026-09",
  status: "live",              // live · building · shelved
  feature: true,               // spans two columns — use it once or twice
  href: "https://…",           // optional click-through
  stats: [["built in", "2 days"], ["runs on", "P100 ×2"]],
  media: {type: "image", src: "media/friday.png"},
}
```

`title` is the only required field. Everything else is optional and the card
just leaves that part out.

Drop the screenshot in `media/`. If you have no screenshot yet, omit `media`
entirely — the card draws a hatched placeholder with the title's initials, so
the page looks finished before it has any content in it.

Nothing else needs editing. The tag filter, the counters at the top, the
sort order and the lightbox are all derived from `WORK`.

## Media types

| type    | field                          |
| ------- | ------------------------------ |
| `image` | `src`                          |
| `video` | `src`, optional `poster` — autoplays muted and loops |
| `embed` | `src` — an iframe              |

## Looking at it

Open `index.html` in a browser. That is the whole workflow.

It is also served on the fleet box at `/showcase`, behind the same login as
the wall. To update that copy:

```
rsync -a --delete ~/showcase/ thebeast:~/fleet/showcase/
```

## Design

The AUTOGOD v7 language: zero radii, 45° chamfers cut top-left and
bottom-right and lit so the bevel reads as a drawn line, diagonal hatch
rules, italic Archivo caps, monotone white on black, drifting star field.
Deliberately self-contained — it shares no stylesheet with the wall so it
cannot be broken by a change over there.
