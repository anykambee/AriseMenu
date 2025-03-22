local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
Rayfield:LoadConfiguration()
local Window = Rayfield:CreateWindow({
    Name = "Arise Crossover",
    Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
    LoadingTitle = "Be Like Sun Jinwoo",
    LoadingSubtitle = "by @anykambe at scriptblox",
    Theme = "Default", -- Check https://docs.sirius.menu/rayfield/configuration/themes
 
    DisableRayfieldPrompts = false,
    DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface
 
    ConfigurationSaving = {
       Enabled = true,
       FolderName = nil, -- Create a custom folder for your hub/game
       FileName = "Big Hub"
    },
 
    Discord = {
       Enabled = true, -- Prompt the user to join your Discord server if their executor supports it
       Invite = "FtZMxhf57D", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
       RememberJoins = false -- Set this to false to make them join the discord every time they load it up
    },
 
    KeySystem = false, -- Set this to true to use our key system
    KeySettings = {
       Title = "Untitled",
       Subtitle = "Key System",
       Note = "No method of obtaining the key is provided", -- Use this to tell the user how to get a key
       FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
       SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
       GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
       Key = {"Hello"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple strings ("hello","key22")
    }
 })
 local Tab = Window:CreateTab("Main", 4483362458)
 local Section = Tab:CreateSection("Automations")
 local Toggle = Tab:CreateToggle({
    Name = "Auto Attack",
    CurrentValue = false,
    Flag = "Toggle2", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        local player = game:GetService("Players").LocalPlayer
        local settings = player:WaitForChild("Settings")
        settings:SetAttribute("AutoAttack", Value)
        if Value == true then
            Rayfield:Notify({
                Title = "Auto Attack Activated",
                Content = "Your Shadows Will attack nearby mobs",
                Duration = 6.5,
                Image = 4483362458,
             })
        end
    end,
})
local Toggle = Tab:CreateToggle({
    Name = "Auto Arise",
    CurrentValue = false,
    Flag = "Toggle3", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        local player = game:GetService("Players").LocalPlayer
        local settings = player:WaitForChild("Settings")
        settings:SetAttribute("AutoArise", Value)
        if Value == true then
            Rayfield:Notify({
                Title = "Auto Arise Activated",
                Content = "After Defeat Enemy Will Try Arise Auto",
                Duration = 6.5,
                Image = 4483362458,
             })
        end
    end,
})


local Section = Tab:CreateSection("Active This Before TeleKILL")
local Toggle = Tab:CreateToggle({
    Name = "AutoClicker",
    CurrentValue = false,
    Flag = "Toggle1", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
    Callback = function(Value)
        local player = game:GetService("Players").LocalPlayer.leaderstats
        local settings = player:WaitForChild("Passes")
        settings:SetAttribute("AutoClicker", Value)
        if Value == true then
            Rayfield:Notify({
                Title = "AutoClicker Unlocked",
                Content = "Now Click On the auto click button in your screen",
                Duration = 6.5,
                Image = 4483362458,
             })
        end
    end,
})

local Section = Tab:CreateSection("Teleport & Kill Inside Dungeon")
local Button = Tab:CreateButton({
    Name = "Telekill",
    Callback = function()
        local UserInputService = game:GetService("UserInputService")
        local player = game.Players.LocalPlayer
        local character = player.Character or player.CharacterAdded:Wait()
        local humanoid = character:FindFirstChildOfClass("Humanoid")
        local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
        
        if not humanoid or not humanoidRootPart then
            warn("Character is missing required components!")
            return
        end
        local Players = game:GetService("Players")
        local player = Players.LocalPlayer
        -- Disable the FlyingFixer script
        local flyingFixer = workspace.__Main.__Players[player.Name].CharacterScripts:FindFirstChild("FlyingFixer")
        if flyingFixer then
            flyingFixer.Disabled = true
        end
        
        -- Define the paths (Only checking parts in workspace.__Main.__Enemies.Server)
        local path = workspace.__Main.__Enemies.Server  -- This path contains the actual parts
        
        -- Function to get all child parts (directly under workspace.__Main.__Enemies.Server)
        local function getPartsFromServer(server)
            local parts = {}
            if server then
                for _, child in ipairs(server:GetChildren()) do
                    if child:IsA("Part") then
                        table.insert(parts, child)  -- Store the part
                    end
                end
            end
            return parts
        end
        
        -- Function to teleport using MoveTo and attack
        local function teleportAndAttack()
            local allEnemyParts = getPartsFromServer(path)
        
            -- Teleport and attack each enemy
            for _, enemyPart in ipairs(allEnemyParts) do
                if enemyPart and enemyPart:IsA("Part") then
                    humanoidRootPart.CFrame = enemyPart.CFrame
                    wait(0.8)
                    enemyPart:Destroy()
                end
            
            end
        end
        teleportAndAttack()
    end,
})


-- Teleports
local Tab1 = Window:CreateTab("Teleports", 4483362458)
local Section = Tab1:CreateSection(" Teleport to Wild Mount & Dungeons")
local Button = Tab1:CreateButton({
    Name = "Find Mount",
    Callback = function()
        local Players = game:GetService("Players")
        local player = Players.LocalPlayer

        -- List of positions to teleport to
        local positions = {
            Vector3.new(3392.090576171875, 135.89764404296875, 86.87832641601562),
            Vector3.new(461.8363342285156, 117.56482696533203, 3439.457763671875),
            Vector3.new(-6177.61962890625, 135.14613342285156, 5520.94189453125),
            Vector3.new(-5939.04931640625, 125.37019348144531, 443.41009521484375),
            Vector3.new(-5422.2646484375, 107.44154357910156, -5497.765625),
            Vector3.new(-730.8063354492188, 145.7216796875, -3610.615234375),
            Vector3.new(4327.447265625, 118.99542236328125, -4809.18310546875)
        }

        -- Function to teleport the character to each position in sequence
        local function teleportToPositions()
            local flyingFixer = workspace.__Main.__Players[player.Name].CharacterScripts:FindFirstChild("FlyingFixer")
            if flyingFixer then
                flyingFixer.Disabled = true
            end    
            local character = player.Character
            if character then
                local humanoidRootPart = character:FindFirstChild("HumanoidRootPart")
                if humanoidRootPart then
                    for _, pos in ipairs(positions) do
                        local appearFolder = workspace:FindFirstChild("__Extra") and workspace.__Extra:FindFirstChild("__Appear")
                        if appearFolder and #appearFolder:GetChildren() > 0 then
                            break
                        end
                        humanoidRootPart.CFrame = CFrame.new(pos) -- Teleporting the character
                        wait(0.4) -- Short delay between each teleport
                    end
                end
            end
        end

        teleportToPositions()

    end,
 })
local Button = Tab1:CreateButton({
    Name = "Find Dungeon",
    Callback = function()
    -- The function that takes place when the button is pressed
    end,
 })
local Section = Tab1:CreateSection(" Teleport Islands")
local Button = Tab1:CreateButton({
    Name = "Leveling City",
    Callback = function()
        
        local flyingFixer = workspace.__Main.__Players[game:GetService("Players").LocalPlayer.Name].CharacterScripts:FindFirstChild("FlyingFixer")
        if flyingFixer then
            flyingFixer.Disabled = true
        end
        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(577, 28, 282))
    end,
 })
local Button = Tab1:CreateButton({
    Name = "Grass Village",
    Callback = function()
        local flyingFixer = workspace.__Main.__Players[game:GetService("Players").LocalPlayer.Name].CharacterScripts:FindFirstChild("FlyingFixer")
        if flyingFixer then
            flyingFixer.Disabled = true
        end
        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(-3122, 44, 2895))
    end,
 })
local Button = Tab1:CreateButton({
    Name = "One Piece Island",
    Callback = function()
        local flyingFixer = workspace.__Main.__Players[game:GetService("Players").LocalPlayer.Name].CharacterScripts:FindFirstChild("FlyingFixer")
        if flyingFixer then
            flyingFixer.Disabled = true
        end
        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(-2839, 50, -2002))
    end,
 })
local Button = Tab1:CreateButton({
    Name = "Bleach Island",
    Callback = function()
        local flyingFixer = workspace.__Main.__Players[game:GetService("Players").LocalPlayer.Name].CharacterScripts:FindFirstChild("FlyingFixer")
        if flyingFixer then
            flyingFixer.Disabled = true
        end
        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(3219, 46, -3772))
    end,
})
local Button = Tab1:CreateButton({
    Name = "Lucky Island",
    Callback = function()
        local flyingFixer = workspace.__Main.__Players[game:GetService("Players").LocalPlayer.Name].CharacterScripts:FindFirstChild("FlyingFixer")
        if flyingFixer then
            flyingFixer.Disabled = true
        end
        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(203, 38, 4329))
    end,
})
local Button = Tab1:CreateButton({
    Name = "Dedu Island",
    Callback = function()
        local flyingFixer = workspace.__Main.__Players[game:GetService("Players").LocalPlayer.Name].CharacterScripts:FindFirstChild("FlyingFixer")
        if flyingFixer then
            flyingFixer.Disabled = true
        end
        game:GetService("Players").LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(3830, 60, 2966))
    end,
})


