# ConfigsManager
ConfigsManager is a simple and efficient CLI application that helps you 
manage your configuration files by associating keys with file paths.

Built with [Cobra CLI](https://github.com/spf13/cobra) library to provide a powerful and user-friendly command line interface.

### With configsManager, you can:
- Manage configs 
- Retrieve config paths by keys
- View content of config files
- List all stored config keys
- Open config files in your preferred editor

# Fast start 
### Linux (x86_64 / AMD64)
```
curl -L https://github.com/hurtki/configsManager/releases/latest/download/cm-linux-amd64 -o cm
chmod +x cm
sudo mv cm /usr/local/bin/
```

### macOS Intel 
```
curl -L https://github.com/hurtki/configsManager/releases/latest/download/cm-darwin-amd64 -o cm
chmod +x cm
sudo mv cm /usr/local/bin/
```

### Linux ARM64
```
curl -L https://github.com/hurtki/configsManager/releases/latest/download/cm-linux-arm64 -o cm
chmod +x cm
sudo mv cm /usr/local/bin/
```

### macOS Apple Silicon(ARM)
```
curl -L https://github.com/hurtki/configsManager/releases/latest/download/cm-darwin-arm64 -o cm
chmod +x cm
sudo mv cm /usr/local/bin/
```
### Windows AMD64 (64-bit)
Download latest release 
https://github.com/hurtki/configsManager/releases/latest/download/cm-windows-amd64.exe

Rename to cm.exe
Place it in a folder that is in the PATH environment variable, for example:
`C:\Users\YourUser\AppData\Local\Microsoft\WindowsApp`

# Usage
`cm [command]`

### Available Commands:
  ### add
  Add a new configuration key with its associated file path
  ```
  cm add [config name] [config absolute/realive path]
  ```
  Auto creating a name for config
  ```
  cm add [config absolute/realive path]
  ```
  Add a new config using stdIN
  ```
  realpath [path] | cm add [config name]/or nothing if you want to auto create a name for config
  ```
  ---
  ### rm
  Remove a config from list by key
  ```
  cm rm [config key]
  ```
  ---
  ### cat
  Print the content of the config file for a given key
  ```
  cm cat [config name]
  ```
  ---
  ### keys
  List all configuration keys
  ```
  cm keys
  ```
  --- 
  ### open
  Open a config in editor
  ```
  cm open [config name]
  ```
  --- 
  ### path
  Retrieve the file path associated with a configuration key
  ```
  cm path  [config name]
  ```
  --- 
  ### help
  Help about any command
  ```
  cm help
  ```

## 🔧 Application Config

Yes, this tool uses a config file!  
You can open it anytime with:

```bash
cm open cm_config
````

The config is automatically created at:
`~/.config/configManager.json`

Example structure:

```json
{
  "editor": "vim",
  "overwrite_if_exists": false,
  "force_add_path": false
}
```

---

### 🖊️ `editor`

**Default:** `"vim"`
This is the command used to open your configuration files.

Example:

```bash
[your_editor_command] /path/to/your/config.cfg
```

---

### ⚠️ `overwrite_if_exists`

**Default:** `false`

* If `false`, the tool will ask you to confirm before overwriting an existing key.
* If `true`, it will overwrite existing keys without asking.

---

### 🛡️ `force_add_path`

**Default:** `false`

* If `false`, the tool will ask for confirmation before adding a path that doesn't exist.
* If `true`, it will add such paths without any confirmation.

---




