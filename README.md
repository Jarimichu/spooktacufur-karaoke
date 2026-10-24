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
the host puts on stage (YouTube full screen, or for Spotify and other links a
card saying to play it from the admin page). It isn't a frame around the app,
because a page inside Google's frames can't autoplay video with sound.

When the admin page is open through `index.html` in the same browser as the
player, the two talk over a `BroadcastChannel` that `index.html` relays: the
player reports its position several times a second, so the admin page's muted
preview stays in step with the TV, and the admin page's play, pause, restart
and progress bar reach the TV at once.

The app itself (and its admin key) lives in a separate, private project.
