# COTGX NDK Ultimate 🚀

Welcome to **COTGX NDK Ultimate**! This is a custom, highly optimized NDK environment designed specifically for Android developers who code on the go. 

Tired of CMake crashing on paths with spaces? Sick of slow build times? This NDK bypasses CMake completely and compiles raw C++ files directly in seconds!

## 🔥 Features
* **Ultra-Fast Compilation:** Compile heavy C++ libraries in under 10 seconds.
* **No CMake Required:** Direct Clang++ compilation.
* **Mobile Optimized:** Built to run smoothly inside Android IDEs (like Code on the Go / AndroidIDE).
* **Pre-configured Sysroot:** Auto-links Android and Log libraries.

## 📦 Installation
1. Go to the **[Releases](../../releases)** section of this repository.
2. Download the `cotgx-ndk-ultimate.tar.gz` file.
3. Extract it to your home directory (`~/cotgx-ndk/`).

## ⚡ How to Use (The 9-Second Master Command)
Navigate to your C++ folder in your terminal and run this master command to compile, strip, and move your `.so` files all at once:

```bash
cd "app/src/main/cpp" && \
~/cotgx-ndk/cotgx-build.sh clang++ -shared -fPIC fileops.cpp -landroid -llog -o libfileops.so && \
~/cotgx-ndk/cotgx-build.sh clang++ -shared -fPIC zipops.cpp -landroid -llog -lz -o libzipops.so && \
~/cotgx-ndk/cotgx-build.sh clang++ -shared -fPIC searchops.cpp -landroid -llog -o libsearchops.so && \
~/cotgx-ndk/cotgx-build.sh clang++ -shared -fPIC hashops.cpp -landroid -llog -o libhashops.so && \
~/cotgx-ndk/cotgx-build.sh clang++ -shared -fPIC sortops.cpp -landroid -llog -o libsortops.so && \
~/cotgx-ndk/cotgx-build.sh strip lib*.so && \
mkdir -p "../../jniLibs/arm64-v8a" && \
mv lib*.so "../../jniLibs/arm64-v8a/" && \
echo "✅ ALL DONE DIRECTLY! NO CMAKE BS!"
