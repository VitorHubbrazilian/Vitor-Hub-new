
-- Load Fluent Library
local Fluent = loadstring(game:HttpGet("https://github.com/dawid-scripts/Fluent/releases/latest/download/main.lua"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/SaveManager.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/dawid-scripts/Fluent/master/Addons/InterfaceManager.lua"))()

-- Create Window
local Window = Fluent:CreateWindow({
    Title = "SPOCK HUB " .. Fluent.Version,
    SubTitle = "by Vitor",
    TabWidth = 160,
    Size = UDim2.fromOffset(580, 460),
    Acrylic = true,
    Theme = "Dark",
    MinimizeKey = Enum.KeyCode.LeftControl
})

-- Tabs
local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "" }),
    Settings = Window:AddTab({ Title = "Settings", Icon = "settings" })
}

local Options = Fluent.Options

-- Notification Example
Fluent:Notify({
    Title = "SPOCK HUB",
    Content = "The script has been loaded.",
    Duration = 8
})

-- Add Auto Farm Button
Tabs.Main:AddButton({
    Title = "Start Auto Farm",
    Description = "Start Auto Farming",
    Callback = function()
        -- Implement Auto Farm functionality here
    end
})

-- Add Auto Quest Button
Tabs.Main:AddButton({
    Title = "Start Auto Quest",
    Description = "Start Auto Quest",
    Callback = function()
        -- Implement Auto Quest functionality here
    end
})

-- Add Keybind for toggling GUI
local Keybind = Tabs.Main:AddKeybind("ToggleGUI", {
    Title = "Toggle GUI",
    Mode = "Toggle",
    Default = "LeftControl", 
    Callback = function(Value)
        print("GUI toggled!", Value)
        -- Code to toggle GUI visibility
    end
})

-- Add Auto Kill Aura
Tabs.Main:AddToggle("AutoKillAura", {
    Title = "Auto Kill Aura",
    Default = false,
    Callback = function(Value)
        print("Kill Aura Toggled:", Value)
        -- Implement Auto Kill Aura functionality here
    end
})

-- Add Race V4 and God Human Activation
Tabs.Main:AddButton({
    Title = "Activate Race V4",
    Description = "Activate Race V4",
    Callback = function()
        -- Implement Race V4 Activation
    end
})

Tabs.Main:AddButton({
    Title = "Activate God Human",
    Description = "Activate God Human",
    Callback = function()
        -- Implement God Human Activation
    end
})

-- Add Weapon Selector
Tabs.Main:AddDropdown("WeaponSelector", {
    Title = "Select Weapon",
    Values = {"Sword", "Guns", "Fist", "Melee", "Devil Fruit"},
    Default = "Sword",
    Callback = function(weapon)
        print("Weapon selected:", weapon)
        -- Code to equip the selected weapon
    end
})

-- Add Auto Raid Functionality
Tabs.Main:AddButton({
    Title = "Start Auto Raid",
    Description = "Start Auto Raid",
    Callback = function()
        -- Implement Auto Raid functionality here
    end
})

-- Add Fast Attack Feature
Tabs.Main:AddToggle("FastAttack", {
    Title = "Enable Fast Attack",
    Default = false,
    Callback = function(Value)
        print("Fast Attack Enabled:", Value)
        -- Implement Fast Attack functionality here
    end
})

-- Add Auto Mobs Kill with CFrame (for efficient farming)
Tabs.Main:AddToggle("AutoMobsKill", {
    Title = "Auto Kill Mobs",
    Default = false,
    Callback = function(Value)
        print("Auto Mobs Kill:", Value)
        -- Implement Auto Kill Mobs using CFrame here
    end
})

-- Implement Event-based Features (such as Sea Events)
Tabs.Main:AddButton({
    Title = "Start Sea Event",
    Description = "Start Sea Event (Shark, Sea Beast, etc.)",
    Callback = function()
        -- Implement Sea Event functionality here (Sharks, Sea Beasts, etc.)
    end
})

-- Add system for activating God Human & Race V4 (Auto Unlock)
Tabs.Main:AddToggle("AutoUnlockRaceV4", {
    Title = "Auto Unlock Race V4",
    Default = false,
    Callback = function(Value)
        print("Auto Unlock Race V4:", Value)
        -- Implement Auto Unlock Race V4 functionality here
    end
})

-- Implement Auto Kill Players in Trials
Tabs.Main:AddButton({
    Title = "Activate Player Kill in Trial",
    Description = "Kill Players in Trial automatically",
    Callback = function()
        -- Implement Player Kill in Trial functionality here
    end
})

-- Add Quest Auto Features
Tabs.Main:AddButton({
    Title = "Start Auto Quest",
    Description = "Automatically complete quests",
    Callback = function()
        -- Implement Auto Quest functionality here
    end
})

-- Add Race and God Human Toggles
Tabs.Main:AddToggle("RaceV4", {
    Title = "Activate Race V4",
    Default = false,
    Callback = function(Value)
        print("Race V4 activated:", Value)
        -- Implement functionality for Race V4
    end
})

Tabs.Main:AddToggle("GodHuman", {
    Title = "Activate God Human",
    Default = false,
    Callback = function(Value)
        print("God Human activated:", Value)
        -- Implement God Human functionality
    end
})

-- Enable Fast Attack (undetectable)
Tabs.Main:AddToggle("SuperFastAttack", {
    Title = "Super Fast Attack (Undetectable)",
    Default = false,
    Callback = function(Value)
        print("Super Fast Attack enabled:", Value)
        -- Implement Super Fast Attack functionality
    end
})

-- Interface and Save Managers
SaveManager:SetLibrary(Fluent)
InterfaceManager:SetLibrary(Fluent)

SaveManager:IgnoreThemeSettings()
SaveManager:SetIgnoreIndexes({})
InterfaceManager:SetFolder("FluentScriptHub")
SaveManager:SetFolder("FluentScriptHub/specific-game")

InterfaceManager:BuildInterfaceSection(Tabs.Settings)
SaveManager:BuildConfigSection(Tabs.Settings)

-- Initial Tab Selection
Window:SelectTab(1)

SaveManager:LoadAutoloadConfig()
