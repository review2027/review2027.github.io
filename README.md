# RE:VIEW 2027 website

Static single-page site for RE:VIEW 2027, the Rethinking the Security and
Future of Peer Review, co-located with ACNS 2027. It uses plain HTML, CSS,
and a little JavaScript, with no build step and no external resources.

```
index.html                    page content
css/style.css                 styles
js/main.js                    mobile menu, e-mail links, smooth scrolling
assets/logo.svg               logo
assets/favicon.svg            browser icon
assets/people/*.jpg           chair photos
assets/founders_building.jpg  banner photo (Founder's Building, from the ACNS 2027 website)
```

## Preview and deployment

Open `index.html` in a browser, or run `python3 -m http.server` in this folder
and go to <http://localhost:8000/>.

The site is published with GitHub Pages from the `main` branch (folder
`/ (root)`) at <{{SITE_URL}}>. Every push to `main` updates the live site
within a minute or two.

## Images

- **Banner:** `assets/founders_building.jpg` is used as the banner background,
  under a dark overlay that keeps the text readable (defined in the `.hero`
  rule in `css/style.css`).
- **Chairs:** the photos are 240 × 240 px, with the head at the same size and
  position on the same light backdrop, and are shown as circles. Replacement
  photos should use the same framing.

## Updating content

- Pending items are shown as `<span class="tba">TBA</span>`. Replace the span
  with the confirmed text. Dates use
  `<time datetime="2027-MM-DD">D Month 2027</time>`.
- Submissions are currently by e-mail to the two chairs (no submission
  system for this first edition). If a HotCRP/EasyChair link opens later,
  replace the "Submission site" entry with `<a href="…">…</a>`, or with a
  button: `<a class="button" href="…">Submit a paper</a>`.
- Contact addresses are written as `name [at] domain [dot] ac [dot] uk` in
  the HTML. `js/main.js` turns every `<a class="email">` written this way
  into a `mailto:` link, so the plain address never appears in the page
  source. The pattern works for any domain, not just acns2027.com.
- Program Committee: replace the TBA span with a list, for example

  ```html
  <ul class="pc-list">
    <li>Name, Affiliation, Country</li>
  </ul>
  ```

- Program: the tentative agenda is already in its own section
  (`#program`, before Organization). Update the table in `index.html` as the
  schedule firms up — its styling lives in the "Program" block of
  `css/style.css`.

Colors and fonts are defined as custom properties at the top of
`css/style.css`.
