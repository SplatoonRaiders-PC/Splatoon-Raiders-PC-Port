# Splatoon Raiders PC Port

Play **Splatoon Raiders** on PC through a Switch 2 emulator. Splatoon PC port, Splatoon 3 PC setup notes, Deep Cut, Spirhalite Islands, gyro, LDN. Play on Windows with Ryujinx or a Yuzu-class emu.

This zip is the PC-side guide + configs, not a ROM. Dump your own keys and game. Deep Cut / Spirhalite Islands notes sit in `files/dock/`.

`keys/setup-manager.ts` is the setup flow. `dock/config.ts` is the emu profile. `ldn/CompatibilityList.ts` is the title / emu matrix. `ldn/LDNManager.ts` is local wireless-style sessions. Tests: `dock/config.test.ts`, `keys/setup-manager.test.ts`. Entry: `keys/main.ts`, `dock/index.ts`. Types: `keys/types.ts`. Helpers: `keys/utils.ts`.

<img width="646" height="318" alt="images1" src="https://github.com/user-attachments/assets/0ae55dd7-222f-48fb-8885-ddd49a524ecd" />
<img width="1920" height="1080" alt="images2" src="https://github.com/user-attachments/assets/70eb6aa3-98f2-4a03-92ae-9f168009f7c1" />

1. Unpack the guide.
2. Install Ryujinx or a Yuzu-class emu.
3. Load your own prod.keys / title.keys and the game dump.
4. Apply `files/dock/config.ts` through `keys/setup-manager.ts`.
5. Check `ldn/CompatibilityList.ts` if the build ID is not the one this pack was written for.

Tag `2026-07-23`. Windows. No firmware in the zip.

<img width="1920" height="1080" alt="images3" src="https://github.com/user-attachments/assets/090715ca-25cc-4749-86ea-bdf4128d372b" />

## Emulators

Ryujinx or Yuzu-class. Keys and the game dump are yours. If the title boots to a black dock, the prod.keys / title.keys pair is incomplete - not a port-broken case.

Splatoon 3 PC searches that want the older title can use the same emu path; this pack's configs are tuned for Raiders (Spirhalite, Deep Cut HUD scale). Compatibility list says which emu revision was last confirmed.

`setup-manager` writes the profile once. Re-running it overwrites local tweaks - copy `config.ts` out if you changed docked resolution by hand.

<img width="1920" height="1080" alt="images4" src="https://github.com/user-attachments/assets/d10331b6-9a1a-4740-a990-1b481c7dd07b" />


## Controls

Pro controller / DualSense, gyro aiming, keyboard binds in the gyro folder. LDN for local wireless-style sessions (`LDNManager.ts`). If gyro drifts, recalibrate in the emu, not in Windows game-controller settings. Keyboard binds are a fallback for menus, not for a ranked match.

<img width="596" height="335" alt="images5" src="https://github.com/user-attachments/assets/09f596ad-0f47-4bb1-b2d8-7f003dd5f7c9" />

## Deep Cut / Spirhalite

Guide notes cover Deep Cut HUD scale and Spirhalite Islands lighting. If the islands look blown out, the emu's resolution scaler is above what the profile expected - drop it in `config.ts`, do not "fix" it with a ReShade preset from a different title.


<img width="739" height="415" alt="images6" src="https://github.com/user-attachments/assets/2927817d-f336-4d5f-9e8c-87c298a59639" />


## Layout

```
files/dock/
files/keys/
files/ldn/
files/gyro/
files/notes/
files/Screenshots/
```

Release notes: `release information/Splatoon Raiders PC.txt`.

## Troubleshooting

| Symptom | Cause |
|---|---|
| Black dock | Incomplete keys |
| LDN empty | `LDNManager` / emu LDN off |
| Gyro drift | Recalibrate in emu |
| Wrong title | Splatoon 3 dump vs Raiders |
| Setup overwrote tweaks | Re-ran setup-manager |

## Notes

Windows. No ROM in the zip. Tag `2026-07-23`.
