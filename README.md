# NovaUI - Roblox UI Library

NovaUI ist eine benutzerfreundliche und anpassbare UI-Library für Roblox, die eine Vielzahl an UI-Komponenten und eine einfache Benutzeroberfläche für Entwickler bietet. Sie ermöglicht das Erstellen von Fenstern, Buttons, Toggles, Keybinds und mehr. Ideal für den Einsatz in Spiel-Hubs und Scripten.

## 📦 Installation

Lade die NovaUI-Bibliothek von GitHub:

```lua
local Nova = loadstring(game:HttpGet("https://raw.githubusercontent.com/N40000-Scripts/NovaUI/refs/heads/main/NovaUI_Main_Module"))()
```

## 🔨 Setup

### 1. Erstelle ein Fenster (Window)

Um ein Fenster zu erstellen, nutze die `CreateWindow` Methode:

```lua
local Window = Nova:CreateWindow({
   Name = "Nova UI Example",
   Theme = "Default",  -- Standard-Theme
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

Tabs ermöglichen es, verschiedene Kategorien von UI-Komponenten zu gruppieren:

```lua
local MainTab = Window:CreateTab("Main")
```

### 3. Erstelle einen Button

Erstelle einen Button, der eine Funktion aufruft, wenn er gedrückt wird:

```lua
local Button = MainTab:CreateButton({
   Name = "Click Me",  -- Text des Buttons
   Callback = function()
      print("Button clicked!")  -- Was passiert, wenn der Button geklickt wird
   end
})
```

### 4. Erstelle einen Toggle

Ein Toggle ist ein Schalter, den man umschalten kann:

```lua
local Toggle = MainTab:AddToggle({
   Name = "Enable Feature",  -- Name des Toggles
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

Ein Slider ermöglicht es, Werte innerhalb eines bestimmten Bereichs auszuwählen:

```lua
local Slider = MainTab:AddSlider({
   Name = "Speed",  -- Name des Sliders
   Min = 0,         -- Minimalwert
   Max = 100,       -- Maximalwert
   Default = 50,    -- Standardwert
   Callback = function(value)
      print("Speed set to: " .. value)
   end
})
```

### 6. Erstelle ein Dropdown-Menü

Mit einem Dropdown-Menü kannst du eine Auswahl von Optionen anzeigen:

```lua
local Dropdown = MainTab:AddDropdown({
   Name = "Select Option",  -- Name des Dropdowns
   Options = {"Option 1", "Option 2", "Option 3"},  -- Optionen im Dropdown
   Default = "Option 1",    -- Standardwahl
   Callback = function(selectedOption)
      print("Selected option: " .. selectedOption)
   end
})
```

### 7. Erstelle einen Keybind

Ein Keybind ist eine Taste, die eine Funktion ausführt, wenn sie gedrückt wird:

```lua
local Keybind = MainTab:AddKeybind({
   Name = "Toggle Fly",  -- Name des Keybinds
   Key = "F",            -- Die Taste, die den Keybind aktiviert
   Callback = function()
      print("Fly key pressed!")  -- Was passiert, wenn der Keybind aktiviert wird
   end
})
```

### 8. Erstelle einen Farbpicker

Ein Farbpicker ermöglicht es, eine Farbe auszuwählen:

```lua
local ColorPicker = MainTab:AddColorPicker({
   Name = "Pick Color",  -- Name des Farbpickers
   DefaultColor = Color3.fromRGB(255, 0, 0),  -- Standardfarbe
   Callback = function(selectedColor)
      print("Selected color: " .. tostring(selectedColor))
   end
})
```

### 9. Erstelle ein Label

Labels werden verwendet, um einfachen Text in der UI anzuzeigen:

```lua
local Label = MainTab:AddLabel({
   Text = "This is a simple label."  -- Text des Labels
})
```

### 10. Erstelle eine Trennlinie

Trennlinien werden verwendet, um visuelle Abgrenzungen zu erstellen:

```lua
local Divider = MainTab:AddLine()
```

### 11. Erstelle einen scrollbaren Bereich

Mit einem scrollbaren Bereich kannst du viele Komponenten auf kleinem Raum unterbringen:

```lua
local ScrollableSection = MainTab:AddScrollableSection({
   Name = "Scrollable Settings",  -- Name des scrollbaren Bereichs
   Height = 300,  -- Maximale Höhe für das Scrollen
   Components = {
      -- Füge hier die Komponenten hinzu, die in den scrollbaren Bereich sollen
   }
})
```

### 12. Wechsel zwischen Themes

Du kannst das Theme der UI jederzeit wechseln:

```lua
Window:ApplyTheme("Red")  -- Setzt das Theme auf Rot
```

### 13. Konfiguration speichern und laden

Um Benutzereinstellungen zu speichern und zu laden:

```lua
-- Speichern
Settings["Aimbot"] = true  -- Beispiel, Toggle speichern
saveConfig()

-- Laden
local currentAimbotSetting = Settings["Aimbot"]
```

### 14. Fenster schließen

Um das Fenster zu schließen:

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
