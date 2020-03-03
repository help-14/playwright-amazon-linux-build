# Build Firefox on Amazon Linux 2

### Create VM to build
- Creat a powerful VM on AWS, build will need lots of disk space and time.
- SSH to VM then go to root: 
```
sudo su -
yum update
```

### Install dependency
Follow the doc for each browser:
- [Chrome](https://github.com/help-14/playwright-amazon-linux-build/blob/master/docs/Chrome.md)
- [Firefox](https://github.com/help-14/playwright-amazon-linux-build/blob/master/docs/Firefox.md)
- [Webkit](https://github.com/help-14/playwright-amazon-linux-build/blob/master/docs/Webkit.md)

### Follow Playwright guide to build browser
- Clone Playwright repo
- Go to repo folder
- Run these command:
```
./browser_patches/prepare_checkout.sh <browser name>
cd ./browser_patches/<browser name>
./build.sh
```
Guide in [here](https://github.com/microsoft/playwright/tree/master/browser_patches)
