# About
This repository provides a keymap for the Lenovo KU-1255 (ThinkPad Compact USB Keyboard with TrackPoint) firmware. The firmware stores key-specific values, generated by XORing the HID Usage ID with 0x5A, at specific offsets within the binary. By modifying these XORed IDs, you can remap any key on the KU-1255. A GUI tool to easily create a key-remapped firmware is also provided.

# Disclaimer
The data in this table is generated from automated firmware analysis using `keymap_offset_finder.py`. **The result accuracy is not assured. Use at your own risk.**

# GUI Tool Usage
1. Download the latest firmware `tp_compact_usb_kb_with_trackpoint_fw.exe` from the [Lenovo official website](https://support.lenovo.com/ca/en/solutions/pd026745).
2. Download the [released application](https://github.com/haborite/ku1255-firmware-keymap/releases/download/v0.4.1/ku1255-fw-remapper-win-0.4.1.zip) and unzip it.
3. Run `ku1255-fw-remapper.exe` in the unzipped directory (It will take a bit time to launch).

<img width="640" alt="gui-overview" src="https://github.com/user-attachments/assets/0134801f-3a95-40c1-a9b2-61cda8a60ef1">

5. Click "1. Select Original Firmware" and select the downloaded firmware `tp_compact_usb_kb_with_trackpoint_fw.exe`.
6. Confirm that the original SHA256 hash is `7116a3819ee094857d21e4671cb6cf953d582372126f0f6728f6b2421eda7bd4`.
7. Click "2. Select Key Remap JSON" and select a key-remap json file (e.g. Use `examples\Swap-Fn-Ctrl.json` to just swap `Fn` and `LeftControl`). If you want to create or modify key-remapping json files, please see the "Offset & XORed ID table" described below.  
5. Click "3. Modify and Save New Firmware", and specify the filename and path of the new firmware.
6. Check SH256 hash (e.g. If you use `Swap-Fn-Ctrl.json`, it should be `123143092dab578550c87a62526b07a6c5f06c047f2455be87971aa51577e300`).
7. Close the app.

# Offset & XORed ID table
|Key Name|HID Usage ID|Offset|XORed ID|
|---|---|---|---|
|A|0x04|0x73fda|0x5e|
|B|0x05|0x7401e|0x5f|
|C|0x06|0x73fec|0x5c|
|D|0x07|0x73fea|0x5d|
|E|0x08|0x73fe6|0x52|
|F|0x09|0x7401a|0x53|
|G|0x0A|0x74012|0x50|
|H|0x0B|0x74022|0x51|
|I|0x0C|0x74036|0x56|
|J|0x0D|0x7402a|0x57|
|K|0x0E|0x7403a|0x54|
|L|0x0F|0x7404a|0x55|
|M|0x10|0x7402c|0x4a|
|N|0x11|0x7402e|0x4b|
|O|0x12|0x74046|0x48|
|P|0x13|0x74056|0x49|
|Q|0x14|0x73fd6|0x4e|
|R|0x15|0x74016|0x4f|
|S|0x16|0x73ffa|0x4c|
|T|0x17|0x74020|0x4d|
|U|0x18|0x74026|0x42|
|V|0x19|0x7401c|0x43|
|W|0x1A|0x73ff6|0x40|
|X|0x1B|0x73ffc|0x41|
|Y|0x1C|0x74030|0x46|
|Z|0x1D|0x73fdc|0x47|
|1|0x1E|0x73fd8|0x44|
|2|0x1F|0x73ff8|0x45|
|3|0x20|0x73fe8|0x7a|
|4|0x21|0x74018|0x7b|
|5|0x22|0x74014|0x78|
|6|0x23|0x74024|0x79|
|7|0x24|0x74028|0x7e|
|8|0x25|0x74038|0x7f|
|9|0x26|0x74048|0x7c|
|0|0x27|0x74058|0x7d|
|Return Enter|0x28|0x7407c|0x72|
|Escape|0x29|0x73fd2|0x73|
|Delete|0x2A|0x74080|0x70|
|Tab|0x2B|0x73fe0|0x71|
|Spacebar|0x2C|0x7407e|0x76|
|Dash and Underscore|0x2D|0x74054|0x77|
|Equals and Plus|0x2E|0x74034|0x74|
|Left Brace|0x2F|0x74060|0x75|
|Right Brace|0x30|0x74040|0x6a|
|Pipe and Slash|0x31|0x7407a|0x6b|
|Non-US|0x32|0x7405c|0x68|
|SemiColon and Colon|0x33|0x7405a|0x69|
|Apostrophe and Double Quotation Mark|0x34|0x74052|0x6e|
|Grave Accent and Tilde|0x35|0x73fd4|0x6f|
|Comma|0x36|0x7403c|0x6c|
|Period|0x37|0x7404c|0x6d|
|QuestionMark|0x38|0x7405e|0x62|
|Caps Lock|0x39|0x74000|0x63|
|F1|0x3A|0x73ff4|0x60|
|F2|0x3B|0x73fe4|0x61|
|F3|0x3C|0x73ff0|0x66|
|F4|0x3D|0x73fe2|0x67|
|F5|0x3E|0x74072|0x64|
|F6|0x3F|0x74032|0x65|
|F7|0x40|0x74050|0x1a|
|F8|0x41|0x74044|0x1b|
|F9|0x42|0x74074|0x18|
|F10|0x43|0x74078|0x19|
|F11|0x44|0x74088|0x1e|
|F12|0x45|0x740a8|0x1f|
|PrintScreen|0x46|0x740ca|0x1c|
|Pause|0x48|0x740bc|0x12|
|Insert|0x49|0x740c8|0x13|
|Home|0x4A|0x74084|0x10|
|PageUp|0x4B|0x740cc|0x11|
|Delete Forward|0x4C|0x740c4|0x16|
|End|0x4D|0x740b8|0x17|
|PageDown|0x4E|0x740ce|0x14|
|RightArrow|0x4F|0x740ae|0x15|
|LeftArrow|0x50|0x740be|0x0a|
|DownArrow|0x51|0x7408e|0x0b|
|UpArrow|0x52|0x740b2|0x08|
|Non-US Slash Bar|0x64|0x73ff2|0x3e|
|International1|0x87|0x7403e|0xdd|
|International2|0x88|0x7404e|0xd2|
|International3|0x89|0x74076|0xd3|
|International4|0x8A|0x74042|0xd0|
|International5|0x8B|0x73fde|0xd1|
|LeftControl|0xE0|0x74004|0xba|
|LeftShift|0xE1|0x74070|0xbb|
|LeftAlt|0xE2|0x74092|0xb8|
|Left GUI|0xE3|0x740b0|0xb9|
|RightControl|0xE4|0x7400c|0xbe|
|RightShift|0xE5|0x7406c|0xbf|
|RightAlt|0xE6|0x7409e|0xbc|
|Fn|0xAF|0x740ba|0xf5|

# Non-exsistent Keys in KU-1255
Only keys in `Keyboard/Keypad Page (0x07)` are listed.
|Key Name|HID Usage ID|XORed ID|Note|
|---|---|---| --- |
|ErrorRollOver|0x01|0x5b||
|Scroll Lock|0x47|0x1d||
|Keypad Num Lock and Clear|0x53|0x09||
|Keypad Forward Slash|0x54|0x0e||
|Keypad Star|0x55|0x0f||
|Keypad Dash|0x56|0x0c||
|Keypad Plus|0x57|0x0d||
|Keypad ENTER|0x58|0x02||
|Keypad 1 and End|0x59|0x03||
|Keypad 2 and Down Arrow|0x5A|0x00||
|Keypad 3 and PageDn|0x5B|0x01||
|Keypad 4 and Left Arrow|0x5C|0x06||
|Keypad 5|0x5D|0x07||
|Keypad 6 and Right Arrow|0x5E|0x04||
|Keypad 7 and Home|0x5F|0x05||
|Keypad 8 and Up Arrow|0x60|0x3a||
|Keypad 9 and PageUp|0x61|0x3b||
|Keypad 0 and Insert|0x62|0x38||
|Keypad Period|0x63|0x39||
|Application|0x65|0x3f||
|Power|0x66|0x3c||
|Keypad Equals|0x67|0x3d||
|F13|0x68|0x32||
|F14|0x69|0x33||
|F15|0x6A|0x30||
|F16|0x6B|0x31||
|F17|0x6C|0x36||
|F18|0x6D|0x37||
|F19|0x6E|0x34||
|F20|0x6F|0x35||
|F21|0x70|0x2a||
|F22|0x71|0x2b||
|F23|0x72|0x28||
|F24|0x73|0x29||
|Keypad Comma|0x85|0xdf||
|International6|0x8C|0xd6||
|LANG1|0x90|0xca||
|LANG2|0x91|0xcb||
|LANG3|0x92|0xc8||
|LANG4|0x93|0xc9||
|LANG5|0x94|0xce||
|Right GUI|0xE7|0xbd||

# For JIS keyboard (0B47208) users
Key names in the JP keymap (日本語配列独自キーのKey Name).
|Key|HID Usage name|
|---|---|
|_|International1|
|ひらがな カタカナ|International2|
|¥|International3|
|変換|International4|
|無変換|International5|
|半角/全角|grave_accent_and_tilde|
|かな カナ|LANG1|
|英数|LANG2|

# Acknowledgements
The firmware binary analysis methodology employed in this project is based on the discussion in the following thread, with particular acknowledgement to @federvieh's insightful comment:
- https://github.com/lentinj/tp-compact-keyboard/issues/32#issuecomment-687659110
- https://github.com/lentinj/tp-compact-keyboard/issues/32
