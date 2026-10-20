# FormFour

**Your loop has nowhere to go, so it never finishes.** FormFour keeps your BPM and your 4 chords and plays 4 bars as the pocket, then writes a contrasting 4-bar bridge (held strings + pedal bass, trumpet answer, or fixed pedal) so the original loop can return as the hook. Export the 8 bars as a seamless WAV plus matching MIDI.

- Static HTML/CSS/JS, no account, no database. Settings stay in localStorage.
- Chairs: acoustic grand piano, upright bass, nylon guitar, trumpet, string ensemble, acoustic kit (FluidR3 GM, CC BY 3.0, Frank Wen).
- Samples pinned to commit `044fab8e1456bfafc5776e86dfd6bb8697149aef` via jsDelivr. Never @main.
- Export: 48 kHz / 24-bit / stereo WAV. Downbeat at sample 0, exact length, tail folded, peak ≤ −1 dBFS. MIDI format 1 with tempo and 4/4, each chair own track.
- Web MIDI: hardware keyboard note on/off. On-screen is fallback.
- Price: $19 one-time (Lemon Squeezy or Gumroad). Free demo plays and exports 4 bars.

## Distinct from yesterday and the rest of the line

| Tool | Job |
| --- | --- |
| DoubleFour | Subdivision / gear change on the same pocket |
| GhostFour | Quiet anticipatory ghosts |
| SpaceFour | Air so the hook can slam |
| **FormFour** | Four bars of contrasting bridge so the loop has a place to go and the track can finish |

Yesterday was DoubleFour (double-time feel). FormFour does not change subdivision. It creates form: a real bridge section.

## Pricing recommendation

One-time **$19**. Sell on Lemon Squeezy (merchant of record) and mirror on Gumroad. Bedroom producers buy focused one-shots in that range. Do not make it a standalone subscription; optional add-on inside Forge Pass. Best place: Lemon Squeezy + link from workinwithai.com next to the other live-chair desks.

## Acceptance (section 9)

1. Export at 92 BPM, 8 bars, 48 kHz → exactly 1,001,739 samples; first transient within 1 ms of sample 0. (Engine designed for this; full Offline render in production path.)
2. Import WAV at bar 1 of 92 BPM DAW, loop 4× — no clicks at seam, no drift. (Tail fold + exact length.)
3. Play, switch tab 30 s, return — stopped cleanly, no stacked notes. (visibilitychange → stop + clear sources.)
4. Change recipe, mutes, BPM while playing — heard within one bar, no restart. (Scheduler reads mutable state every step.)
5. Block sample host, reload — UI names missing instruments. (Preload reports which failed.)
6. Longest pad sustains to end of note. (Held strings use long duration + release ramp.)
7. Grep: no @main or @gh-pages, no Math.random in export path, voice names match samples.

## License

MIT source. Commercial desk gated by license key (demo accepts BF- keys). Replace with real Lemon Squeezy / Gumroad verification for sales.

Deploy on Vercel team `release-forge`. Permanent live: https://bridgefour.vercel.app/ (after deploy).
