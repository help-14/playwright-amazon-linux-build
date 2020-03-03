# Build Chrome on Amazon Linux 2

### Prepair

- Download [build-chrome.sh](https://github.com/help-14/playwright-amazon-linux-build/blob/master/scripts/build-chrome.sh) and [.gclient](https://github.com/help-14/playwright-amazon-linux-build/blob/master/scripts/.gclient).
- Switch to `root` user and copy file `build.sh` to `home` of root.
- Make folder `build/chromium`. Copy file `.gclient` to `build/chromium`.
- Run command: `export VERSION=72.0.3585.0`.

### Build Chrome

- Run file `build.sh` with command: `sh build.sh`.
- Wait script running..., it may take longer.
- Chrome headless build file storage in: `/root/bin` (aka /root/bin/headless-chromium).
