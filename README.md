# D.S Link Client

D.S Link is Dimension Stone's branded Windows remote-access client, built from the open-source RustDesk 1.4.9 codebase.

## What this build changes

- Shows **D.S Link** in the Windows client and remote-session title.
- Uses the D.S Link artwork for the Windows, taskbar and tray icons.
- Starts remote sessions with the connection toolbar collapsed. It remains available when needed.
- Keeps the underlying RustDesk configuration identity so existing IDs and settings can continue to work.
- Leaves connection awareness visible on the controlled machine for safe use around CNC and saw controls.

The Windows XP CNC must remain on RustDesk Legacy. This modern Flutter client is for the newer Windows PCs only.

## Build it on GitHub

No local compiler setup is required.

1. Open the repository's **Actions** tab.
2. Select **Build D.S Link Client**.
3. Select **Run workflow**.
4. When both jobs are green, open the completed run.
5. Download the **DSLink-Client-1.4.9-unsigned** artifact.
6. Extract it and run `DSLink.exe`.

Changing the workflow, branding patch or icons on `main` starts another build automatically.

## First test

1. Test on P360 or another modern office PC while no machine is actively being operated.
2. Exit the installed RustDesk interface before opening the portable `DSLink.exe`; keep the working installation available as a fallback.
3. Confirm the existing ID, permanent password and self-hosted server settings are present.
4. Connect in both directions.
5. Confirm the remote toolbar starts collapsed, the session title says D.S Link, and the taskbar icon is the D.S Link symbol.
6. Confirm unattended access, keyboard, mouse, clipboard, multiple monitors and reconnection after reboot.
7. Roll the build out to the remaining modern PCs only after this test passes.

## Important notes

- The binary is unsigned, so Windows SmartScreen or antivirus may warn. Code signing is the proper production fix.
- Some diagnostic text may still mention RustDesk because RustDesk remains the underlying engine.
- This repository deliberately contains no machine IDs, passwords, private keys or server addresses.
- Keep the current LAN-only network layout; building the client does not require exposing ports to the internet.

## Source and licensing

The build is pinned to RustDesk tag 1.4.9 and commit `6c578292e8ebbbec708b76986ba8c4bc7c509747`. D.S Link's patch and build workflow are published here under AGPL-3.0 to preserve the upstream license requirements. See `LICENSE-NOTICE.md` for attribution and source details.
