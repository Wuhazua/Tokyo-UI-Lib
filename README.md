# Tokyo-UI-Lib

# Roblox UI Library Documentation

This document provides a guide on how to use the Roblox UI Library.

## Initialization

```lua
local Decimals = 4
local Clock = os.clock()
local ValueText = "Value Is Now :"

local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/drillygzzly/Roblox-UI-Libs/main/1%20Tokyo%20Lib%20(FIXED)/Tokyo%20Lib%20Source.lua"))({
    cheatname = "Title Here", -- watermark text
    gamename = "Title Here", -- watermark text
})

library:init()
```

## Creating a Window

```lua
local Window1  = library.NewWindow({
    title = "Title Here | Title Here", -- Main window Text
    size = UDim2.new(0, 510, 0.6, 6)
})
```

## Adding Tabs

```lua
local Tab1 = Window1:AddTab("  Tab1  ")
local SettingsTab = library:CreateSettingsTab(Window1)
```

## Adding Sections

```lua
local Section1 = Tab1:AddSection("Section 1", 1)
```

## Adding Elements to a Section

### Toggle

```lua
Section1:AddToggle({
    text = "Toggle1",
    state = false,
    risky = true,
    tooltip = "tooltip1",
    flag = "Toggle_1",
    risky = false,
    callback = function(v)
        print(ValueText, v)
    end
})
```

### Toggle with Bind

```lua
Section1:AddToggle({
    text = "Toggle1",
    state = false,
    risky = true,
    tooltip = "tooltip1",
    flag = "Toggle_1",
    risky = false,
    callback = function(v)
        print(ValueText, v)
    end
}):AddBind({
    enabled = true,
    text = "Keybind1",
    tooltip = "tooltip1",
    mode = "toggle",
    bind = "None",
    flag = "ToggleKey_1",
    state = false,
    nomouse = false,
    risky = false,
    noindicator = false,
    callback = function(v)
        print(ValueText, v)
    end,
    keycallback = function(v)
        print(ValueText, v)
    end
})
```

### TextBox

```lua
Section1:AddBox({
    enabled = true,
    name = "TextBox1",
    flag = "TextBox_1",
    input = "PlaceHolder1",
    focused = false,
    risky = false,
    callback = function(v)
        print(ValueText, v)
    end
})
```

### Separator

```lua
Section1:AddSeparator({
    enabled = true,
    text = "Separator1"
})
```

### Button

```lua
Section1:AddButton({
    enabled = true,
    text = "Button1",
    tooltip = "tooltip1",
    confirm = true,
    risky = false,
    callback = function()
        print("Pressed!")
    end
})
```

### Slider

```lua
Section1:AddSlider({
    enabled = true,
    text = "Slider1",
    tooltip = "tooltip1",
    flag = "Slider_1",
    suffix = "",
    dragging = true,
    focused = false,
    min = 0,
    max = 100,
    increment = 0.1,
    risky = false,
    callback = function(v)
        print(ValueText, v)
    end
})
```

### List

```lua
Section1:AddList({
    enabled = true,
    text = "Selection", 
    tooltip = "tooltip1",
    selected = "",
    multi = false,
    open = false,
    max = 4,
    values = {"1", "2", "3"},
    risky = false,
    callback = function(v)
        print(ValueText, v)
    end
})
```

### Color Picker

```lua
Section1:AddColor({
    enabled = true,
    text = "Color1",
    tooltip = "tooltip1",
    color = Color3.fromRGB(255, 255, 255),
    flag = "Color_1",
    trans = 0,
    open = false,
    risky = false,
    callback = function(v)
        print(ValueText, v)
    end
})
```

## Notification

```lua
local Time = (string.format("%."..tostring(Decimals).."f", os.clock() - Clock))
library:SendNotification(("Loaded In "..tostring(Time)), 6)
```
