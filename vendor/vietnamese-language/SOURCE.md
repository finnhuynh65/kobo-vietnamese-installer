# Vietnamese language source

The translation, library, and udev rule were copied unchanged from the official [`redphx/kobo-tieng-viet`](https://github.com/redphx/kobo-tieng-viet) release `v20260319` (`KoboRoot.tgz`, SHA-256 `3854122f591d9038b8083d6af55796340ed4b0f5954ee43a7da83cbf1b7f683f`). The configuration script is locally modified as described below.

Original project and author: **Kobo Tiếng Việt by redphx**.

- `trans_vi.qm` provides the Vietnamese Kobo interface translation.
- `libtiengviet.so` contains upstream keyboard hooks and automatic font repair. It is retained here for provenance only and is excluded from generated packages.
- `update_conf.sh` and `update_conf.rules` add `vi` to Kobo's `ExtraLocales` and select it as the current locale during installation. The modified script first moves an existing library to `/mnt/onboard/.adds/tiengviet/libtiengviet.so.disabled`, outside Nickel's plugin directory.

The language pack can be installed independently of the fonts. It does not install NickelMenu, KOReader, keyboard hooks, or automatic font repair. Reapply the font fix after a firmware update if Vietnamese rendering breaks. Reinstall the language pack and restart Kobo to disable a plugin from an earlier installation; a font-only install does not disable it.
