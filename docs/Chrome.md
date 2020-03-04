# Build Chrome on Amazon Linux 2

Pick an Instance Type with at least 16 GB of memory. Compile time will take about 4-5 hours on a t2.xlarge, or 2-3ish on a t2.2xlarge or about 45 min on a c4.4xlarge. Give yourself a Root Volume that's at least 30 GB (40 GB if you want to compile a debug build—which you won't be able to upload to Lambda because it's too big.)

### Prepair

- Download [build-chrome.sh](https://github.com/help-14/playwright-amazon-linux-build/blob/master/scripts/build-chrome.sh) and [.gclient](https://github.com/help-14/playwright-amazon-linux-build/blob/master/scripts/.gclient).
- Switch to `root` user and copy file `build.sh` to `home` of root.
- Make folder `build/chromium`. Copy file `.gclient` to `build/chromium`.
- Find chromium version on [Playwright](https://github.com/microsoft/playwright), example: 82.0.4057.0
- Run command: `export VERSION=82.0.4057.0`.

### Build Chrome

- Run file `build.sh` with command: `sh build.sh`.
- Wait script running..., it may take longer.
- Chrome headless build file storage in: `/root` (aka `/root/chromium.zip`).
