# calabash-android-cloud9
It's a perfect image to use to start android test automation using `calabash-android`. It also have `manymo` command installed so can use manymo.com's emulator.

Using internal avd is not recommended since it's still terribly slow.

## `minimum` branch
Slim down image size from 4GB to 2GB by:
* Base on codenvy/android image
* Removed rbenv (don't use it that much)
* Removed Android SDK update step. Base image is already on SDK 23

## `master` branch
Built based on `codenvy/android442`. Added `rbenv`. Updated the android sdk. And sprayed `cloud9` on top of it.

It's a perfect image to use to start android test automation using `calabash-android`. It also have `manymo` command installed so can use manymo.com's emulator.


## Usage
Use this `docker-compose.yml` to start:
```yml
x:
  image: neofreko/calabash-android-cloud9
  ports:
   - 6080
   - 4200
   - 8080
  volumes:
    - ~/:/workspace
```

Port `6080` exposes the vnc. When VirtualBox -- or your native linux host supports
HAXM -- you can use the built in emulator instead of opting for manymo. (master branch only)

Port `4200` is codenvy original web tty  (master branch only)

Port `8080` is cloud9. Cloud9 terminal is a better option than codenvy one.

No git, so you have to use it from the host.
