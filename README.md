# NovaUI - Roblox UI Library

NovaUI ist eine benutzerfreundliche und anpassbare UI-Library für Roblox, die eine Vielzahl an UI-Komponenten und eine einfache Benutzeroberfläche für Entwickler bietet. Sie ermöglicht das Erstellen von Fenstern, Buttons, Toggles, Keybinds und mehr. Ideal für den Einsatz in Spiel-Hubs und Scripten.

## 📦 Installation

1. **Lade die NovaUI-Lib**
   Du kannst NovaUI direkt von einem Hosting-Dienst (z. B. GitHub) laden:

   ```lua
   local Nova = loadstring(game:HttpGet("https://raw.githubusercontent.com/N40000-Scripts/NovaUI/refs/heads/main/NovaUI_Main_Module"))()
   ```

2. **Integriere NovaUI in dein Skript/Projekt:**
   Erstelle eine neue Instanz von `NovaUI` und verwende sie, um UI-Komponenten zu erstellen.

## 🔨 Setup

### 1. Erstelle ein Fenster (Window)

```lua
local Window = Nova:CreateWindow({
   Name = "Nova UI Example",
   Theme = "Default",
   ConfigurationSaving = {
      Enabled = true,
      FileName = "MyNovaSettings"
   },
   KeySystem = true,
   KeySettings = {
      Title = "Nova Hub",
      Subtitle = "Access Key Required",
      Note = "Get the key from our Discord: discord.gg/example",
      FileName = "NovaKeyFile",
      SaveKey = true,
      Key = {"test123", "key456"}
   }
})
```

### 2. Erstelle einen Tab

```lua
local MainTab = Window:CreateTab("Main")
```

### 3. Erstelle einen Button

```lua
local Button = MainTab:CreateButton({
   Name = "Click Me",
   Callback = function()
      print("Button clicked!")
   end
})
```

### 4. Erstelle einen Toggle

```lua
local Toggle = MainTab:AddToggle({
   Name = "Enable Feature",
   Default = false,  -- Standardwert für den Toggle
   Callback = function(state)
      if state then
         print("Feature enabled!")
      else
         print("Feature disabled!")
      end
   end
})
```

### 5. Erstelle einen Slider

```lua
local Slider = MainTab:AddSlider({
   Name = "Speed",
   Min = 0,          -- Minimalwert
   Max = 100,        -- Maximalwert
   Default = 50,     -- Standardwert
   Callback = function(value)
      print("Speed set to: " .. value)
   end
})
```

### 6. Erstelle ein Dropdown-Menü

```lua
local Dropdown = MainTab:AddDropdown({
   Name = "Select Option",
   Options = {"Option 1", "Option 2", "Option 3"},
   Default = "Option 1",  -- Standardwahl
   Callback = function(selectedOption)
      print("Selected option: " .. selectedOption)
   end
})
```

### 7. Erstelle einen Keybind

```lua
local Keybind = MainTab:AddKeybind({
   Name = "Toggle Fly",
   Key = "F",  -- Standardtaste
   Callback = function()
      print("Fly key pressed!")
   end
})
```

### 8. Erstelle einen Farbpicker

```lua
local ColorPicker = MainTab:AddColorPicker({
   Name = "Pick Color",
   DefaultColor = Color3.fromRGB(255, 0, 0),  -- Rote Farbe als Standard
   Callback = function(selectedColor)
      print("Selected color: " .. tostring(selectedColor))
   end
})
```

### 9. Erstelle ein Label

```lua
local Label = MainTab:AddLabel({
   Text = "This is a simple label.",
})
```

### 10. Erstelle eine Trennlinie

```lua
local Divider = MainTab:AddLine()
```

### 11. Erstelle einen scrollbaren Bereich

```lua
local ScrollableSection = MainTab:AddScrollableSection({
   Name = "Scrollable Settings",
   Height = 300,  -- Maximale Höhe für das Scrollen
   Components = {
      -- Füge hier die Komponenten hinzu, die in den scrollbaren Bereich sollen
   }
})
```

### 12. Wechsel zwischen Themes

```lua
Window:ApplyTheme("Red")  -- Wechselt zu einem vordefinierten "Red"-Theme
```

### 13. Konfiguration speichern und laden

```lua
-- Speichern
Settings["Aimbot"] = true  -- Beispiel, Toggle speichern
saveConfig()

-- Laden
local currentAimbotSetting = Settings["Aimbot"]
```

### 14. Fenster schließen

```lua
Window:Close()
```

## 🛠️ Funktionen

* **Fenster erstellen**: `CreateWindow({})`
* **Tabs erstellen**: `CreateTab("TabName")`
* **UI-Komponenten hinzufügen**:

  * Button: `CreateButton({})`
  * Toggle: `AddToggle({})`
  * Slider: `AddSlider({})`
  * Dropdown: `AddDropdown({})`
  * Keybind: `AddKeybind({})`
  * Farbpicker: `AddColorPicker({})`
  * Label: `AddLabel({})`
  * Trennlinie: `AddLine()`
  * Scrollbarer Abschnitt: `AddScrollableSection({})`

## ⚙️ Einstellungen

NovaUI unterstützt das Speichern und Laden von Benutzereinstellungen. Du kannst die Einstellungen für jedes Element speichern und automatisch wiederherstellen.

### Beispiel:

```lua
Settings["Aimbot"] = true  -- Speichern des Aimbot-Status
saveConfig()  -- Speichert die Konfiguration
```

## 🎨 Dynamisches Theme

Du kannst das Theme in Echtzeit wechseln, um das Aussehen deiner UI anzupassen:

```lua
Window:ApplyTheme("Red")  -- Setzt das Theme auf Rot
```

## 📥 Lizenz

NovaUI ist unter der MIT-Lizenz verfügbar. Siehe die [LICENSE](LICENSE) für Details.

---

### ⚠️ Hinweis:

Diese Library ist primär für die Verwendung in Roblox Scripts und UIs gedacht. Sie kann in Hub-Skripten oder anderen benutzerdefinierten Projekten verwendet werden, um benutzerfreundliche und interaktive Oberflächen zu erstellen.
