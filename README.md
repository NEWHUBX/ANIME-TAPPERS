local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/xHeptc/Kavo-UI-Library/main/source.lua"))()
local Window = Library.CreateLib("NEW_HUB", "DarkTheme")
local Tab = Window:NewTab("Main")
local Section = Tab:NewSection("NEW_HUB")

local Tab = Window:NewTab("Auto Fram")
local Section = Tab:NewSection("Auto Click")
Yens = {}

Section:NewToggle("Auto Click", "", function(ads)
_G.Click = ads
while _G.Click do wait()
local Event = game:GetService("ReplicatedStorage").Remotes.Events.Tap
Event:FireServer()
    end
end)
------------------------------
local Section = Tab:NewSection("Auto Yen")
for i,v in pairs(game:GetService("Workspace").Worlds:GetChildren()) do
    table.insert(Yens,v.Name)
    end
Section:NewDropdown("Selcet Worlds", "", Yens, function(abc)
    Selcet = abc
end)
Section:NewToggle("Auto Yen", "", function(state)
_G.Yen = state
while _G.Yen do wait()
for i,v in pairs(game:GetService("Workspace").Worlds[Selcet].Yen:GetDescendants()) do
if v.Name == "TouchInterest" then
    game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Parent.CFrame
wait(.2)
    end
end
end
end)
