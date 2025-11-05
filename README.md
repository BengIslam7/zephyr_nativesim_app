# zephyr_nativesim_app

# Zephyr Project (Native Simulation)

This project demonstrates a simple Zephyr application built and executed using the **native_sim** board target.
The `native_sim` board allows you to run Zephyr applications directly on your host PC (Linux, macOS, or Windows) without physical hardware.

---

## ⚙️ Build

Clean and build the project using the `native_sim` board target:

```bash
west build -b native_sim --pristine
```

* `-b native_sim`: Specifies the target board for simulation.
* `--pristine`: Ensures a clean build by deleting the previous build directory.

---

## 🚀 Run

After building, run the generated executable:

```bash
build/zephyr/zephyr.exe
```

Or, depending on your system:

```bash
./build/zephyr/zephyr.exe
```

If you are using Linux, the output will appear in your terminal, for example:

```
*** Booting Zephyr OS build v3.x.x ***
Hello World! native_sim
```

---

## 🧹 Clean the Build

To remove all generated build files:

```bash
west build -t clean
```

or simply delete the build directory:

```bash
rm -rf build
```

---

## 📝 Notes

* The `native_sim` board is ideal for testing Zephyr applications on your host without hardware.
* To build for a real board, replace `native_sim` with your board name (e.g., `nucleo_f746zg`).

---