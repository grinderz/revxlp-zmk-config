# RevXLP42 Choc — ZMK config

ZMK firmware configuration for the 42-key RevXLP (Seeeduino XIAO /
XIAO BLE / XIAO RP2040).

- ZMK is pinned to a stable release in `config/west.yml` (`# zmk-revision` marker).
- `config/boards/shields/revxlp` — shield definition (works on both ZMK v0.x and main).
- `config/revxlp.keymap` — the keymap, synced from
  [mriya46-mx](https://github.com/grinderz/mriya-zmk-config/tree/mriya46-mx) and
  adapted to 42 keys; `config/revxlp.json` — layout for
  [keymap-editor](https://nickcoutsos.github.io/keymap-editor/).
- [ZMK Studio](https://zmk.dev/docs/features/studio) is supported via the
  `*_studio` firmware (USB connection); unlock with the `&studio_unlock` key on
  the Control layer.
- Layer diagrams and the flashing guide live in the umbrella repo:
  [zmk-buildroot](https://github.com/grinderz/zmk-buildroot).

## Building

GitHub Actions builds every target from `build.yaml` on push.

Local Docker builds are driven from the umbrella repository
([zmk-buildroot](https://github.com/grinderz/zmk-buildroot)), which includes
this repo as a submodule:

```sh
make revxlp42-choc                 # every firmware target of this keyboard
make revxlp42-choc-xiao-ble        # a single target
make ZMK_REV=main PRISTINE=1 revxlp42-choc   # against ZMK main
```
