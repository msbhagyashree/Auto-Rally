# Auto Rally

A cute auto-rickshaw racing game for your phone. Race 3 laps, grab coins, dodge cows and beat your best time.

It is **one small file** (about 19 KB) with no internet needed. Play it on a train, in flight mode, anywhere.

## Play it

### On a phone (offline)

1. Send `auto-rally.html` to the phone (WhatsApp, email, AirDrop, USB or Google Drive).
2. Open the file in **Chrome** (Android) or **Safari** (iPhone).
3. Tap **START RACE**.
4. For the flight-mode test: open it once, then switch on flight mode and play again.

On Android you can also use *Add to Home screen* to get a launcher icon.

### On a laptop

Double-click `auto-rally.html`. Steer with the arrow keys (or A and D).

## How to play

- Your auto **drives itself**. You only steer.
- The **left and right buttons** (or the left / right arrow keys, or A / D) steer.
- The **BRAKE** button (or down arrow, S or Space) slows you down for sharp turns.
- **Coins** are collected and counted. They come back every lap.
- **Turbo** (the lightning pickup) gives a speed boost for about 2.6 seconds.
- **Cones** (orange) and **cows** bump you and slow you down. Cones get knocked away. Cows stay put.
- **Grass** slows you down but never crashes you.
- Finish 3 laps as fast as you can. Your best time is saved.

Other keys: **M** mutes or unmutes. **Enter** or **Space** starts a race from the menu.

## Features

| Requirement | How it works |
|---|---|
| Driveable auto-rickshaw on a looping road | Top-down view, smooth looped track with curbs, a checkered start line and a minimap |
| Keyboard and touch controls | Arrow keys / WASD, plus large on-screen buttons that handle two thumbs at once |
| Coins, obstacles, power-up | Coins, cones, cows, and the turbo power-up |
| 3 laps with a timer | Countdown 3-2-1-GO, live timer, lap splits on the finish screen |
| Best time that stays saved | Saved on the device (see "Saved best time" below) |
| Sound with a mute button | Engine hum that follows your speed, plus coin, crash, turbo, lap and finish sounds. Mute button at the top right |

## Fair play

- **Crashes:** a hit keeps 35% of your speed (it never stops you), then gives you 1.2 seconds of flashing safety so you can't be hit twice in a row.
- **Obstacles** always leave a clear gap to drive through. The layout is the same every race, so friends can learn the track and compare times fairly.
- **Laps** count by distance driven along the road. Reversing can't cheat a lap, and cutting across the grass doesn't help because the grass is slow.
- **Wrong way:** a "WRONG WAY" warning appears if you head backwards.
- A soft invisible edge pushes you back toward the road if you drive far into the grass.

## Saved best time

Your best time is stored in the browser's local storage on that device (key `ar_best`; the mute choice is `ar_mute`).

- Works in Chrome on Android and on desktop, and when the game is hosted on a website.
- **iPhone Safari can be unreliable for files opened from the phone's storage.** Test it by finishing a race, closing the browser fully, reopening the file and checking the best time on the start screen.
- Clearing browser data or using a private window erases it.

## Sound

Phones only allow sound after the first tap, so audio starts when you press START RACE. The sound is generated in code (no audio files).

## Tuning the game

All the numbers are in the `<script>` of `auto-rally.html`. The easiest ones to change:

| What | Where to look | Current value |
|---|---|---|
| Top speed | `mx=(car.off?140:300)` | 300 (140 on grass) |
| Turbo strength and length | `bo?1.45:1` and `car.boost=2.6` | 1.45 times speed for 2.6 s |
| Steering | `steer*2.6` | 2.6 |
| Road width | `const W=190` | 190 |
| Track size | `S=1.3` | 1.3 (bigger = longer laps) |
| Crash safety time / speed kept | `car.inv=1.2;car.v*=.35` | 1.2 s / 35% |
| Number of laps | `k>=3` and the "/3" texts | 3 |

A test run with a simple autopilot finished 3 laps in about 81 seconds (about 27 seconds a lap). Faster players will be quicker.

## Done-when checklist

- [ ] A full race plays on a real phone in flight mode.
- [ ] A friend finishes a race without you explaining anything.
- [ ] Crashes and lap counts feel fair (note which turn or obstacle felt unfair so it can be tuned).
- [ ] The best time survives closing and reopening the game.

## Built with

Plain HTML, CSS and JavaScript on one canvas. Sounds come from the Web Audio API. No libraries, no images, no network calls.