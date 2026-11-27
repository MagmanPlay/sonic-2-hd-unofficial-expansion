# Unofficial Expansion Patch v1

Changes from Team S2HD’s original Windows Demo 2.0, build 1012.

## New playable zones

- **Aquatic Ruin Zone** adds two acts between Chemical Plant and Hill Top. The layouts follow the 1992 Mega Drive game, including the upper and underwater routes. Both acts use eph’s Aquatic Ruin Act 1 arrangement. Act 2 ends with the Egg Hammer fight.
- **Mystic Cave Zone** adds two acts after Hill Top, with mine railways, hanging vines, moving crates and spike traps. Both acts use Tee Lopes’ Mystic Cave arrangement. Egg Digger waits at the end of Act 2.
- The campaign now has five zones and ten acts. The playable order is **Emerald Hill → Chemical Plant → Aquatic Ruin → Hill Top → Mystic Cave**. Direct level starts use that same order and skip unreleased zones. To start a new act directly, use `S2HD.exe --level arz --act 1` or `S2HD.exe --level mcz --act 2`.

## Settings and controls

- **Options → Game → Roll Jump Lock.** On (default) keeps the original restriction on steering when you jump out of a roll. Off lets you steer left or right in the air after a rolling jump. Ordinary jumps handle the same in both modes. The game remembers your choice.
- **Options → Video → Refresh Rate.** Auto (default) follows the current display, including refresh rates outside the preset list. Manual choices are **50, 60, 75, 90, 100, 120, 144, 165, 180, 200, 240, 280, 300, 360 and 480 Hz**. If the display rate cannot be read, Auto falls back to 60 Hz.
- The Game settings have their own panel in the pause menu. The Video panel fits all six rows, including the refresh-rate selector. Removed the stray dotted arrow outside that panel.
- **Enter** or **numpad Enter** finishes the end-of-act bonus tally immediately. The remaining bonus is added to your score once.
- Both new zones ship with HD graphics enabled. For the classic artwork in either zone, move its `aquatic-ruin-hd.dat` or `mystic-cave-hd.dat` out of the `mods` folder and restart. Keep the matching gameplay pack in place.

## Camera, campaign and rendering

- The camera eases into the finish line without the sharp upward snap. A charged spin dash can no longer leave the signpost crossing off-screen.
- After a boss fight, the camera centres on the capsule during the results tally, even if the player lands on the edge of the button.
- The campaign fades into the next zone. The transition from Act 1 to Act 2 was checked at both running and spin-dash speeds in all five zones, with Sonic and Tails grounded after the handoff.
- Characters, moving objects and the camera draw smoothly between the game’s fixed **60 physics updates per second**. Pausing holds the last displayed positions. A stationary character on a support no longer shifts back and forth by a pixel.
- Fixed a renderer bug that dropped tiles already queued for the frame when a busy scene needed more space. It could make scenery disappear or flash black for a frame.
- The expansion’s HD art packs now load after their matching gameplay packs regardless of the order Windows lists the files.
- The startup screens credit Team S2HD for the original game and MagmanPlay for the independent expansion. The title screen identifies the installed patch beside the original build number.

## Gameplay and boss logic

- Across all five boss fights, Eggman laughs when the main character is hurt, including hits from a projectile. If the player survives, the fight continues. If the player loses a life, the machine and its attached parts hold position while Eggman keeps laughing. In Chemical Plant, the cockpit splash no longer hides that reaction.
- Breathing underwater follows the game clock. A full supply lasts **30 seconds**. During the last 12 seconds the main character sees **5, 4, 3, 2, 1, 0**, one number every two seconds. The sidekick no longer draws a duplicate countdown. Taking air or surfacing clears the warning.
- Fixed a bug in the original bubble object where growing a large air bubble changed its type. A fully grown air bubble can now replenish the player’s air.
- Shield and invincibility effects keep animating when a character is hanging from an object. Collision-layer switches ignore invalid path numbers and keep the character on the current path.
- Losing a life during an act title card now clears the card’s update state so the normal retry or game-over sequence can take over.

## Audio

- Speed Shoes switch to the faster music at the same point in the tune, including after a loop, and return to the matching point when the effect wears off. Picking up another pair while the effect is active keeps the music playing.
- Added the missing fast versions for **Chemical Plant Act 2** and the **Hill Top co-op music in Acts 1 and 2**. Speed Shoes music is also supported in both expansion zones.
- Fixed how the original demo reads and saves **master, music and sound-effect volume** on systems that use a decimal comma. Old settings such as `0,5` are read correctly. Out-of-range values are clamped and invalid entries fall back to the default.

## Credits

Team S2HD created Sonic 2 HD, the SonicOrca engine and Demo 2.0. MagmanPlay made this independent fan expansion. Sonic the Hedgehog and the original Sonic the Hedgehog 2 belong to SEGA. Original zone music by Masato Nakamura, with arrangements by eph and Tee Lopes. Some expansion artwork was made with the help of ImageGen.
