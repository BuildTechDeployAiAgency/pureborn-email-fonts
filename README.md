# Fonts

Pureborn uses three font families. See `docs/technical-spec.md` §4 for the
rendering strategy (short version: Century Gothic = live text, others = PNG images).

## Files

| File | Family | Usage | License status |
|---|---|---|---|
| `CenturyGothic.otf` | Century Gothic Regular | Body copy, nav links | ⚠️ Monotype — desktop license does NOT cover webfont/email embedding. Either confirm Pureborn has a webfont license, or use fallback stack only. |
| `CenturyGothic-Bold.otf` | Century Gothic Bold | Button labels, emphasized body | ⚠️ Same as above |
| `Typo_Round_Bold_Demo.otf` | Typo Round Bold | Display headlines | ⚠️ Demo version — commercial use likely not permitted. Verify license before @font-face embedding. Currently rendered as PNG-only per technical spec. |
| `ThrowMyHandsUpintheAirBold.ttf` | Throw My Hands Up in the Air | Script accent phrases | ⚠️ Free font — verify terms of commercial use. Currently rendered as PNG-only per technical spec. |

## Action items

Before embedding any of these as @font-face in production:

1. Get Pureborn legal/brand to confirm commercial email licensing for each.
2. If no license: use Google Fonts alternatives and fallback stacks (suggestions in technical spec).
3. If licensed: host the fonts on a Pureborn-controlled CDN (not email attachment) and reference via @font-face with cross-origin headers.

## Fallback stacks (safe to ship today)

Body text:
```css
font-family: 'Century Gothic', 'Apple Gothic', 'URW Gothic L', 'Avant Garde', sans-serif;
```

Rounded display (if dropping Typo Round):
```css
font-family: 'Quicksand', 'Fredoka', 'Trebuchet MS', Verdana, sans-serif;
```

Script (DO NOT use a fallback — render as image instead, or fall back to italic serif if truly unavoidable):
```css
font-family: 'Caveat Brush', 'Kalam', cursive, serif;
```
