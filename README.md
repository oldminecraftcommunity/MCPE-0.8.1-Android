# MCPE 0.8.1 for Android
Decompiled MCPE 0.8.1 APK. **Does not contain `res` and `assets` that are neccessary to build it**(get them from the original apk yourself).

## Preparing to build
* Clone this repo
* Recursively clone MCPE-0.8.1 repo into `app/src/main/cpp` (`git clone https://github.com/oldminecraftcommunity/MCPE-0.8.1 app/src/main/cpp --recursive`)
* Use jadx(or similar tool) to get `res` folder from apk file(while the apk already contains `res` folder, some of its content is packed into `resources.arsc`)
* Extract `assets` and `libminecraftpe.so` from the original apk
* move `assets` and `res` folders to `app/src/main/`
* Run `python app/src/main/cpp/tools/get_sound_data.py <path/to/libminecraftpe.so>` and move the resulted `pcm_data.c` file into `app/src/main/cpp/minecraftpe/impl/`
  * Make sure you extracted armv7 libminecraftpe.so and not x86 or else sound data will be incorrect!
## Building
* You should be able to build this project by using `./gradlew build`
* Alternatively you can open this project in android studio and build it there.
