# omarchy-bluetooth-rfkill

Fork of the built-in Omarchy `omarchy.bluetooth` bar widget.

On some machines (e.g. ThinkPad T580, `tpacpi_bluetooth_sw`) the rfkill soft block
used by `omarchy-bluetooth-power off` removes the controller from BlueZ. The stock
widget hides itself when there is no adapter (`visible: adapter !== null`), so
Bluetooth can no longer be switched back on from the bar.

Changes vs. upstream:
- widget is always visible
- without an adapter it shows the "off" icon/text
- toggling without an adapter runs `omarchy-bluetooth-power on`

Install: symlink this folder to `~/.config/omarchy/plugins/taiku.bluetooth` and use
`taiku.bluetooth` in `shell.json` instead of `omarchy.bluetooth`.
