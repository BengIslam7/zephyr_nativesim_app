# zephyr_nativesim_app

[![CI/CD Pipeline](https://github.com/BengIslam7/zephyr_nativesim_app/actions/workflows/ci.yml/badge.svg)](https://github.com/BengIslam7/zephyr_nativesim_app/actions/workflows/ci.yml)

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

## 📦 CI/CD Pipeline

This project includes a GitHub Actions CI/CD pipeline that automatically builds and optionally releases firmware for Zephyr boards.

### Workflow Triggers

The pipeline runs on:

* Pushes to `main` or `develop` branches.
* Pushes of tags matching `v*.*.*`.
* Pull requests targeting `main` or `develop`.
* Manual workflow dispatch.

### Jobs

1. **Build**:

   * Checks out the repository.
   * Installs host dependencies (CMake, Ninja, Python, etc.).
   * Sets up a Python virtual environment and installs `west`.
   * Initializes the Zephyr workspace and installs required packages and SDK.
   * Builds the firmware for the specified board(s) (`native_sim` by default).
   * Uploads the firmware artifacts (`zephyr.exe` and `zephyr.elf`).

2. **Release**:

   * Downloads the firmware artifact from the build job.
   * Creates a GitHub Release and attaches the firmware files.

---

## 📝 Notes

* The `native_sim` board is ideal for testing Zephyr applications on your host without hardware.
* To build for a real board, replace `native_sim` with your board name (e.g., `nucleo_f746zg`).
* The CI/CD workflow ensures your firmware is automatically built and optionally released on GitHub.

---