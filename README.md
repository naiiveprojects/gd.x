# <img src="./assets/icon.png" width="28"> gd.x

gd.x is a custom Godot Engine 3.x branch with several modifications. Its primary objective is to automate the process of building the latest Godot Engine, reduce binary size, and simplify the workflow for adding modules or making modifications with minimal drawbacks.

### Features

- Optimize for size.
- Enable Full Link-Time Optimization (LTO).
- Disable Visual Script.
- Disable Deprecated Features.
- Disable Debug Symbol.
- Encrypt scripts for security. (`secrets.ENCRYPTION_KEY`)

### Additional

- revamp icon & logo
- [WIP] revamp build-in theme
- Auto width ItemList, Rebase & fix issue [#398548](https://github.com/godotengine/godot/pull/39848)
- Minizip API [#34444](https://github.com/godotengine/godot/pull/34444)

---

## Motive

Compiling Godot Engine from source can be time-consuming and resource-intensive. Moreover, Godot Engine packages all export templates together, resulting in large download sizes, which may not always be necessary.

## Build

| Platform         | Build Type          | Architecture       |
|------------------|---------------------|--------------------|
| Windows          | `Editor`, `Release` | 64-bit             |
| MacOS            | -                   | -                  |
| Linux            | `Release`           | 64-bit             |
| HTML5 (Javascript)| `Release`, `Thread`| -                  |
| Android          | `Release`           | arm 7              |
| iOS              | -                   | -                  |

### values

- **Build Types**   : `Editor`, `Debug`, `Release`, `Thread`, `GDNative`
- **Architectures**  : 32-bit, 64-bit, arm 7, arm 64

## How-To

### Use

> ⚠️ **Attention**
>
> please note that it is not a stable build and considered *bleeding-edge*. Therefore, **backing up your projects / utilizing version control systems like Git is highly recommended.**

- When exporting, use the `Custom Template` pointing to the build binary. You can safely ignore the "No export template found at the expected path" warning message.

### Modify

> 🟢 The `assets` directory will overwrite the contents of the working directory. This approach provides flexibility for modifying the Godot Engine source code without altering the workflow.

- `Modules` : copy the module to assets/modules directory

### Cloning

- in settings > Secrets and variables > Actions
  - create a **New Repository secret**
    - **name** `ENCRYPTION_KEY`
    - **secret** YOUR_ENCRYPTION_KEY
- in settings > Actions > General > Workflow permissions
  - set to **Read and write permission** to give github action permission in this case to create new release

### Refrences

- [Godot Engine GitHub Repository](https://github.com/godotengine/godot)
- [Compiling Godot Engine](https://docs.godotengine.org/en/stable/contributing/development/compiling/index.html)
- [Optimizing for Size](https://docs.godotengine.org/en/3.6/development/compiling/optimizing_for_size.html)
- [Script Encryption](https://docs.godotengine.org/en/3.6/development/compiling/compiling_with_script_encryption_key.html)
- [Base Action Template](https://github.com/Fractural/GodotBuilds/tree/3.x)
