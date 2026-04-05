# COTGX NDK Ultimate 🚀

Welcome to **COTGX NDK Ultimate**! This is a custom, highly optimized NDK environment designed specifically for Android developers who code on the go.

Tired of CMake crashing on paths with spaces? Sick of slow build times? This NDK bypasses CMake completely and compiles raw C++ files directly in seconds!

---

## ⚠️ Before You Start — One-Time Setup (IMPORTANT)

If you get a `wget: command not found` error, it means `wget` is not installed on your system. Run this **once** before doing anything else:

```bash
pkg install wget -y
```

> 💡 **Alternative (No wget needed):** You can also use `curl` to download — it comes pre-installed on most COTG/Termux setups. The `curl` download command is given in Step 1 below.

---

## 📦 1. Installation (Follow Carefully)

**Step 1 — Download (Pick ONE method):**

Using `wget` (after installing it via `pkg install wget -y`):
```bash
wget https://your-release-link-here/cotgx-ndk-ultimate.tar.gz
```

Using `curl` (no extra install needed):
```bash
curl -L -o cotgx-ndk-ultimate.tar.gz https://your-release-link-here/cotgx-ndk-ultimate.tar.gz
```

> 📌 Replace the URL above with the actual download link from the **Releases** section of this repo.

**Step 2 — Extract:**

```bash
tar -xvzf cotgx-ndk-ultimate.tar.gz -C ~/
```

**Step 3 — Set Permissions (CRITICAL):**

```bash
chmod +x ~/cotgx-ndk/cotgx-build.sh
```

> Without this step you will get a `Permission Denied` error every time.

**Step 4 — Clean Up (Optional):**

```bash
rm cotgx-ndk-ultimate.tar.gz
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

| Error | Fix |
|---|---|
| `wget: command not found` | Run `pkg install wget -y` first, then retry |
| `Permission Denied` | Run `chmod +x ~/cotgx-ndk/cotgx-build.sh` again |
| `No such file or directory` | Make sure you extracted to `~/cotgx-ndk/` exactly |
| Download failing | Try the `curl` method instead of `wget` |

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
