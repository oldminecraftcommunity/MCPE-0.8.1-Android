# MCPE 0.8.1 for Android
Decompiled MCPE 0.8.1 APK. **Does not contain `res` and `assets` that are neccessary to build it**(get them from the original apk yourself).

## Preparing to build
* Clone the repo with `--recursive` flag(or use `git submodule init` and `git submodule update` after cloning if you forgot to add it)
* Use jadx(or similar tool) to get `res` folder from apk file(while the apk already contains `res` folder, some of its content is packed into `resources.arsc`)
* Extract `assets` and `libminecraftpe.so` from the original apk
* move `assets` and `res` folders to `app/src/main/`
* Run `python app/src/main/cpp/tools/get_sound_data.py <path/to/libminecraftpe.so>` and move the resulted `pcm_data.c` file into `app/src/main/cpp/minecraftpe/impl/`
## Building
* You should be able to build this project by using `./gradlew build`
* Alternatively you can open this project in android studio and build it there.
