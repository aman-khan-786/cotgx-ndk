# COTGX NDK Ultimate 🚀

Welcome to **COTGX NDK Ultimate**! This is a custom, highly optimized NDK environment designed specifically for Android developers who code on the go.

Tired of CMake crashing on paths with spaces? Sick of slow build times? This NDK bypasses CMake completely and compiles raw C++ files directly in seconds!

---

## 📦 1. Installation (Follow Carefully)

To avoid any permission or path issues, follow these exact steps in your terminal:

**Step 1 — Download:**
Go to the **Releases** section and download `cotgx-ndk-ultimate.tar.gz`.

**Step 2 — Move & Extract:**
Move the file to your home directory and extract it:

```bash
tar -xvzf cotgx-ndk-ultimate.tar.gz -C ~/
```

**Step 3 — Set Permissions (CRITICAL):**
You must give execution permission to the compiler script, otherwise you will get a `Permission Denied` error:

```bash
chmod +x ~/cotgx-ndk/cotgx-build.sh
```

---

## ⚡ 2. How to Use (The 9-Second Master Command)

Navigate to your project's C++ source folder (usually `app/src/main/cpp`) and run this single master command.

It will **Compile → Strip → Move** all your `.so` files to the correct folder automatically:

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
```

---

## 🛠️ 3. Troubleshooting

**Error: `Permission Denied`?**
```bash
chmod +x ~/cotgx-ndk/cotgx-build.sh
```
This usually happens if you extracted the file using a normal File Manager instead of the terminal.

**Error: `No such file or directory`?**
Ensure you extracted the tool exactly to `~/cotgx-ndk/`. If the path is different, the master command will not work.

**Architecture Support:**
This NDK is built specifically for **AArch64 (arm64-v8a)** devices.

---

## 🔥 4. Features at a Glance

| Feature | Detail |
|---|---|
| ⚡ Ultra-Fast | Compiles heavy C++ libraries in under 10 seconds |
| 📦 Standalone | No dependency on CMake or external desktop build tools |
| 🔧 Pre-configured | Automatically links `libandroid` and `liblog` by default |
| 📱 Mobile-First | Designed for on-device compilation (Termux, AndroidIDE, COTG) |

---

## 👨‍💻 Developed By

**Aman** — Moderator @ [Code on the Go](https://t.me/CodeOnTheGoOfficial)

> Empowering mobile developers with real NDK power! 💪
