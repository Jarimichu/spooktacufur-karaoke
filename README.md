# Spooktacufur Karaoke

The public page for the Spooktacufur karaoke signup queue:
https://jarimichu.github.io/spooktacufur-karaoke/

`index.html` shows the queue's Google Apps Script web app full-screen in a
frame. Opened directly, an Apps Script web app owned by a personal Google
account gets a "created by a Google Apps Script user" banner; framed by
another site, it doesn't. The page's query string is passed through to the
app:

- `/` - signup (what the QR code opens)
- `/?page=display` - crowd screen
- `/?page=admin&key=...` - host controls

`player.html?key=...` is the video TV: click Start once and it plays whoever
the host puts on stage (YouTube full screen, Spotify embed, or a card saying to
open the link by hand). It isn't a frame around the app, because a page inside
Google's frames can't autoplay video with sound.

The app itself (and its admin key) lives in a separate, private project.
