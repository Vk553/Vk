# PS4 WebKit Exploit (11.00 – 13.00)

A static WebKit exploit chain for the PlayStation 4. Everything runs in the
console's browser, so any static web host will serve it.

Based on SLOPKIT by Jordy, originally written for the PS5. Our team ported it to
PS4 and brought the `lapse` and `poops` kernel exploits onto it to cover
firmware up to 13.00.

## Firmware support

The chain is selected automatically from the browser's User-Agent.

| Firmware | Chain | Tested on hardware |
| -------- | ----- | ------------------ |
| 11.00 | lapse | Yes |
| 11.50 | lapse | Yes |
| 12.00 | lapse | Yes |
| 12.02 | lapse | Yes |
| 12.50 | poops | Yes |
| 12.52 | poops | Yes |
| 13.00 | poops | Yes |

## Usage

1. Open the browser on your PS4 and go to https://rawgame4.github.io/
2. Wait for `CACHED (first run)`. This stores everything in AppCache so later
   runs work offline.
3. Press X to start.

The exploit is not deterministic. A failed attempt usually crashes the browser
or reboots the console, so just reload and try again. If it keeps failing after
a lot of reloads, close the browser fully and reopen it.

Options:

| Parameter | Effect |
| --------- | ------ |
| `?bug=lapse` / `?bug=poops` | Force a chain instead of detecting firmware |
| `?verbose=1` | Full log lines instead of the compacted form |
| `?slots=N` | Override the carrier array size |
| `?payload=1` | Run the payload even if kernel patching was skipped |
