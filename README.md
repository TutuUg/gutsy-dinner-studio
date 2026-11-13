# Gutsy End of Year Dinner Poster Studio

A single-page web app for the Gutsy End of Year Dinner. Guests add a selfie, enter their name, and download a PNG poster saying "I will be attending." to share on social media. Every poster carries the event details and RSVP numbers.

Everything runs in the browser. Photos are never uploaded anywhere.

## Features

- Upload a photo or take a selfie (the front camera opens on phones)
- Drag to move the photo, scroll or pinch to zoom, or drop an image onto the poster
- Name tag over the photo with the guest's name and message (default: "I will be attending.")
- Fixed event footer with date, venue, dress code, price and RSVP numbers. It has no controls on the page, so guests cannot change it.
- 4 templates: Night Market, Block Party, Sunrise, Gallery Label
- 3 photo shapes: circle, arch, square
- 6 accent colors
- 3 export sizes: 1080x1080 (square), 1080x1350 (portrait 4:5), 1080x1920 (story 9:16)
- Light and dark interface

## Files

- `index.html`: the whole app, including the embedded Gutsy logo mark
- `README.md`, `LICENSE`

## Run locally

No build step. Open `index.html` in a browser, or serve it:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Publish with GitHub Pages

1. Push this repo to GitHub as a **public** repository (for example `gutsy-dinner`).
2. Go to **Settings > Pages**.
3. Under **Build and deployment**, set Source to **Deploy from a branch**, Branch to `main`, folder `/ (root)`, then Save.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

After you push an update, GitHub Pages redeploys within a minute or two. Do a hard refresh to see the change.

## Change the event details

The fixed details are in the `EVENT` object near the top of the script in `index.html`:

```js
var EVENT = {
  title: ['END OF YEAR', 'DINNER'],
  tagline: 'Celebrating the mileage, the memories & the people.',
  date: 'Saturday, 12th Dec 2026',
  venue: 'Kabira Country Club',
  dress: 'Casual All White',
  price: 'UGX 150,000',
  rsvp: ['+256 782 048 520', '+256 703 829 923']
};
```

Edit the values and push. The page runs in each visitor's browser, so a technical user could still change the footer on their own copy using browser developer tools. That only affects a poster they make themselves, never the live site.

## Other defaults

In the `state` object just below `EVENT`: `message` ("I will be attending.") and `name`. The accent colors are in the `ACCENTS` array, and the footer colors are `NAVY`, `ORANGE` and `BLUE` at the top of the script.

## Notes

- Fonts (Archivo, Big Shoulders Display and Montserrat) load from Google Fonts. If they are blocked, the app falls back to system fonts.
- The Gutsy mark (runners and wordmark) is embedded as a base64 PNG on the line starting with `mark.src = 'data:image/png;base64,`. It is recolored per template.

## License

MIT. See `LICENSE`.
