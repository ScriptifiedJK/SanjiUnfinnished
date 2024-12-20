-- Sanji


local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("1").Base

local ToolName = baseButton.ToolName


ToolName.Text = "Blazing Blitz" -- put the name of the base move 1


local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("2").Base

local ToolName = baseButton.ToolName


ToolName.Text = "Flaming Concasser" -- put the name of the base move 2


local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("3").Base

local ToolName = baseButton.ToolName


ToolName.Text = "Inferno Kick" -- put the name of the base move 3


local player = game.Players.LocalPlayer

local playerGui = player.PlayerGui

local hotbar = playerGui:FindFirstChild("Hotbar")

local backpack = hotbar:FindFirstChild("Backpack")

local hotbarFrame = backpack:FindFirstChild("Hotbar")

local baseButton = hotbarFrame:FindFirstChild("4").Base

local ToolName = baseButton.ToolName


ToolName.Text = "Flame Reversal" -- put the name of the base move 4


local Players = game:GetService("Players")

local player = Players.LocalPlayer

local playerGui = player:WaitForChild("PlayerGui")


local function findGuiAndSetText()

    local screenGui = playerGui:FindFirstChild("ScreenGui")

    if screenGui then

        local magicHealthFrame = screenGui:FindFirstChild("MagicHealth")

        if magicHealthFrame then

            local textLabel = magicHealthFrame:FindFirstChild("TextLabel")

            if textLabel then

                textLabel.Text = "Diable Jambe" -- put the name of the ult name ultimate text

            end

        end

    end

end
-- ult bar
-- Services
local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")

-- Local Player
local player = Players.LocalPlayer
local playerGui = player:WaitForChild("PlayerGui")

-- GUI and color adjustment function
local function updateBarColor()
    -- Find the ScreenGui on the screen
    local screenGui = playerGui:FindFirstChild("ScreenGui")
    if not screenGui then return end

    -- Find the MagicHealth Frame
    local magicHealthFrame = screenGui:FindFirstChild("MagicHealth")
    if not magicHealthFrame then return end

    -- Find the Health Frame
    local healthFrame = magicHealthFrame:FindFirstChild("Health")
    if not healthFrame then return end

    -- Find the Bar Frame
    local barFrame = healthFrame:FindFirstChild("Bar")
    if not barFrame then return end

    -- Find the ImageLabel with ImageColor3 property inside the Bar Frame
    local imageLabel = barFrame:FindFirstChild("Bar")
    if not imageLabel or not imageLabel:IsA("ImageLabel") then return end

    -- Set the color to yellow
    imageLabel.ImageColor3 = Color3.fromRGB(255, 128, 0) -- Yellow
end

-- Check the GUI again when the character resets
local function onCharacterAdded(character)
    -- Update the GUI
    updateBarColor()
end

-- Check the local player's character
local function onPlayerAdded()
    local character = player.Character or player.CharacterAdded:Wait()
    onCharacterAdded(character)

    -- Check again when the character changes
    player.CharacterAdded:Connect(onCharacterAdded)
end

-- Check when the player is added
Players.PlayerAdded:Connect(onPlayerAdded)
if player then
    onPlayerAdded()
end
-- end of ult bar
-- garou trail changer
local char = game.Players.LocalPlayer.Character

-- Left Arm WaterPalm and WaterTrail Color Change
getgenv().LArmCol = char['Left Arm'].ChildAdded:Connect(function(pp)
    if pp.Name == 'WaterPalm' then
        for i, v in pairs(pp:WaitForChild('ConstantEmit'):GetChildren()) do
            v.Color = ColorSequence.new{
                ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 128, 0)), 
                ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 128, 0))
            }
        end

        pp:WaitForChild('WaterTrail').Color = ColorSequence.new{
            ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 128, 0)), 
            ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 128, 0))
        }
    end
end)

-- Effects Color Change
getgenv().CCol = char.ChildAdded:Connect(function(pp)
    if pp.Name == 'Effects' then
        for i = 1, 55 do
            for _, v in pairs(pp:GetDescendants()) do
                if v:IsA('ParticleEmitter') then
                    v.Color = ColorSequence.new{
                        ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 128, 0)), 
                        ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 128, 0))
                    }
                end
            end
            task.wait()
        end
    end
end)

-- Right Arm WaterPalm and WaterTrail Color Change
getgenv().RArmCol = char['Right Arm'].ChildAdded:Connect(function(pp)
    if pp.Name == 'WaterPalm' then
        for i, v in pairs(pp:WaitForChild('ConstantEmit'):GetChildren()) do
            v.Color = ColorSequence.new{
                ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 128, 0)), 
                ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 128, 0))
            }
        end
        pp:WaitForChild('WaterTrail').Color = ColorSequence.new{
            ColorSequenceKeypoint.new(0.00, Color3.fromRGB(255, 128, 0)), 
            ColorSequenceKeypoint.new(1.00, Color3.fromRGB(255, 128, 0))
        }
    end
end)

-- color trail garou 
--[[Execute Anims (Animations when you execute script]]
 
local p = game.Players.LocalPlayer
local Humanoid = p.Character:WaitForChild("Humanoid")
 
for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do
    animTrack:Stop()
end
 
local AnimAnim = Instance.new("Animation")
AnimAnim.AnimationId = "rbxassetid://18435303746" -- Replace with your animation ID
 
local Anim = Humanoid:LoadAnimation(AnimAnim)
 
local startTime = 0 
 
Anim:Play()
Anim:AdjustSpeed(0)
Anim.TimePosition = startTime
Anim:AdjustSpeed(1)

--END OF EXECUTE ANIM

-- move 1

playerGui.DescendantAdded:Connect(findGuiAndSetText)

findGuiAndSetText()


local animationId = 12273188754 -- the anim that will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then


local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18181589384" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0.8 -- WHERE THE ANIM WILL START


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(0.5)


    end
end
-- end of move 1

-- move 2
humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 12296113986 -- the move that it will track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then


local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://17097275344" -- the specific move ur gonna replace

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for the specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(2)
delay(2.1, function()
 
    Anim:Stop()
 
 end)
     wait(0.2)
local Test = game.ReplicatedStorage.Resources.AtomicFX.MainEffect.Slash1
local test = Test:Clone()
test.Parent = game.Players.LocalPlayer.Character["HumanoidRootPart"]

for _, child in ipairs(test:GetChildren()) do
    if child:IsA("ParticleEmitter") then
        child:Emit(15)
        child.Enabled = true
		        child.Color = ColorSequence.new(Color3.new(255, 0.5, 0))
        child:Emit(15)
        child.Enabled = true
    end
end
    wait(1.6)
	test:Destroy()
    end

end

-- end of move 2

--finisher move 2
humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 14798608838 -- the move that it will track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then


local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18464362124" -- the specific move ur gonna replace

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for the specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1.7)

    end
end

-- end of finisher move 2

-- move 3

humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 12309835105 -- the anim that will track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then


local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://17889471098" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(0.7)

      wait(0.4)
local Test = game.ReplicatedStorage.Resources.FiveSeasonsFX.CharFX.ArmBurst.Attachment
local test = Test:Clone()
test.Parent = game.Players.LocalPlayer.Character["Right Leg"]

for _, child in ipairs(test:GetChildren()) do
    if child:IsA("ParticleEmitter") then
        child:Emit(15)
        child.Enabled = true
		        child.Color = ColorSequence.new(Color3.new(255, 0.5, 0))
        child:Emit(15)
        child.Enabled = true
    end
end
    wait(1.5)
	test:Destroy()
    end

end

-- end of move 3

--finisher move 3
humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 12447247483 -- the move that it will track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then


local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18464362124" -- the specific move ur gonna replace

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for the specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1.6)

    end
end

-- end of finisher move 3

-- not hit move 4

humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 12351854556 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18181589384" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0.42 -- the speed for specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(0)
delay(1.8, function()
 
    Anim:Stop()
 
 end)

    end

end

-- end of not hit move 4

-- move 4 hit

humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local animationId = 13603396939 -- the specific anim that will get track

local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")

local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then
        local p = game.Players.LocalPlayer
        local Humanoid = p.Character:WaitForChild("Humanoid")

        -- Create a new animation instance for the specific animation
        local AnimAnim = Instance.new("Animation")
        AnimAnim.AnimationId = "rbxassetid://17799224866" -- the specific anim

        local Anim = Humanoid:LoadAnimation(AnimAnim)

        local startTime = 0 -- the speed for the specific anim

        Anim:Play()
        Anim:AdjustSpeed(0)
        Anim.TimePosition = startTime
        Anim:AdjustSpeed(0.8)

        -- Add delay before stopping the animation
        task.wait(2.0)  -- Wait for 2 seconds before stopping the animation
        Anim:Stop()  -- Stop the animation

    end

end

-- end of move 4

-- ult move 1
humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local animationId = 12460977270 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://10466974800" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for specific anim

Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)
      wait(0.2)
local Test = game.ReplicatedStorage.Resources.KJEffects.KJWallCombo.FinalImpact.Attachment
local test = Test:Clone()
test.Parent = game.Players.LocalPlayer.Character["HumanoidRootPart"]

for _, child in ipairs(test:GetChildren()) do
    if child:IsA("ParticleEmitter") then
        child:Emit(40)
        child.Enabled = true
    end
end
   wait(2.5)
   test:Destroy()
	

    end

end

-- end of ult move 1

-- ult move 2 start 
humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local animationId = 12463072679 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18897119503" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for specific anim

Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1.2)

    end

end

-- end of ult move 2 start

-- ult move 2 hit
humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local animationId = 12467789963 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18896229321" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 3 -- speed for specific anim

Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(2)
    wait(1)
local Test = game.ReplicatedStorage.Resources.KJEffects.DropkickExtra.lastimpact.Attachment
local test = Test:Clone()
test.Parent = game.Players.LocalPlayer.Character["HumanoidRootPart"]

for _, child in ipairs(test:GetChildren()) do
    if child:IsA("ParticleEmitter") then
        child:Emit(15)
        child.Enabled = true
    end
end
   wait(1.7)
   test:Destroy()
    end

end
-- end of ult move 2 hit

-- ult move 3
humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local animationId = 14057231976 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18440398084" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for specific anim

Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(0.5)
delay(1.3, function()
 
    Anim:Stop()
 
 end)

    end

end
-- end of ult move 3

-- ult move 4
humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local animationId = 16082123712 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://12983333733" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 2 -- speed for specific anim

Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)
      wait(1)
local Test = game.ReplicatedStorage.Resources.FiveSeasonsFX.CharFX.ArmFX
local test = Test:Clone()
test.Parent = game.Players.LocalPlayer.Character["Right Arm"]

for _, child in ipairs(test:GetChildren()) do
    if child:IsA("ParticleEmitter") then
        child:Emit(50)
        child.Enabled = true

    end
end
        wait(4)

            test:Destroy()
    end

end

-- end of ult move 4

-- wall combo

humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local animationId = 16310343179 -- the anim that will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://18181589384" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- speed for the specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(0.65)


    end

end

-- end of wall combo

-- ult anim

humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 12342141464 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://15285521399" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- the specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(0.56)
delay(4.6, function()
 
    Anim:Stop()
 
 end)
    end

end

-- the end of ult anim

-- front dash

humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 13380255751 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://10479335397" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- the specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(0.7)


delay(1.06, function()

    Anim:Stop()

end)

local Test = game.ReplicatedStorage.Resources.EsperAwakening.Aura.Ambient
local test = Test:Clone()
test.Parent = game.Players.LocalPlayer.Character["HumanoidRootPart"]

for _, child in ipairs(test:GetChildren()) do
    if child:IsA("ParticleEmitter") then
        child:Emit(15)
        child.Enabled = true
		        child.Color = ColorSequence.new(Color3.new(255, 0, 0))
        child:Emit(15)
        child.Enabled = true
    end
end
    wait(0.8)
	test:Destroy()
end
    end

-- end of front dash

-- mini uppercut

humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 105033812381 -- the anim will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://14900168720" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 1.3 -- the speed for specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)


    end

end

-- end of mini upper cut

-- downslam

humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 10470104242 -- the anim that will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://12684185971" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- the speed for specific anim


wait(0.2)

Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)


    end

end

-- end of downslam

-- m1s
-- 1st m1
humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 13532562418  -- the anim that will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://17889471098 " -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- the speed for specific anim

Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)


    end

end
-- 2nd m1 
humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 13532600125  -- the anim that will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://17889461810" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- the speed for specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)


    end

end
-- 3rd m1
humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 13532604085  -- the anim that will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://17889471098" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- the speed for specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)


    end

end
--4th m1
humanoid.AnimationPlayed:Connect(onAnimationPlayed)


local animationId = 13294471966  -- the anim that will get track


local player = game.Players.LocalPlayer

local character = player.Character or player.CharacterAdded:Wait()

local humanoid = character:WaitForChild("Humanoid")


local function onAnimationPlayed(animationTrack)

    if animationTrack.Animation.AnimationId == "rbxassetid://" .. animationId then

local p = game.Players.LocalPlayer

local Humanoid = p.Character:WaitForChild("Humanoid")


for _, animTrack in pairs(Humanoid:GetPlayingAnimationTracks()) do

    animTrack:Stop()

end


local AnimAnim = Instance.new("Animation")

AnimAnim.AnimationId = "rbxassetid://17889461810" -- the specific anim

local Anim = Humanoid:LoadAnimation(AnimAnim)


local startTime = 0 -- the speed for specific anim


Anim:Play()

Anim:AdjustSpeed(0)

Anim.TimePosition = startTime

Anim:AdjustSpeed(1)


    end

end
-- end of m1s
isAnimating = true

local replacementAnimationId = replacementAnimations[tostring(animationId)]

if replacementAnimationId then
    local AnimAnim = Instance.new("Animation")
    AnimAnim.AnimationId = replacementAnimationId

    local Anim = humanoid:LoadAnimation(AnimAnim)
    Anim:Play()

    Anim.Stopped:Connect(function()
        isAnimating = false
        if #queue > 0 then
            local nextAnimationId = table.remove(queue, 1)
            playReplacementAnimation(nextAnimationId)
        end
    end)
else
    isAnimating = false
end -- Added missing end here.

local function stopSpecificAnimations()
    for _, track in ipairs(humanoid:GetPlayingAnimationTracks()) do
        local animationId = tonumber(track.Animation.AnimationId:match("%d+"))
        if animationIdsToStop[animationId] then
            track:Stop()
        end
    end
end

local function onAnimationPlayed(animationTrack)
    local animationId = tonumber(animationTrack.Animation.AnimationId:match("%d+"))
    if animationIdsToStop[animationId] then
        stopSpecificAnimations()
        animationTrack:Stop()

        local replacementAnimationId = replacementAnimations[tostring(animationId)]
        if replacementAnimationId then
            playReplacementAnimation(animationId)
        end
    end
end

humanoid.AnimationPlayed:Connect(onAnimationPlayed)

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

local function onBodyVelocityAdded(bodyVelocity)
    if bodyVelocity:IsA("BodyVelocity") then
        bodyVelocity.Velocity = Vector3.new(bodyVelocity.Velocity.X, 0, bodyVelocity.Velocity.Z)
    end
end

character.DescendantAdded:Connect(onBodyVelocityAdded)

for _, descendant in pairs(character:GetDescendants()) do
    onBodyVelocityAdded(descendant)
end

player.CharacterAdded:Connect(function(newCharacter)
    character = newCharacter
    humanoidRootPart = character:WaitForChild("HumanoidRootPart")
    character.DescendantAdded:Connect(onBodyVelocityAdded)

    for _, descendant in pairs(character:GetDescendants()) do
        onBodyVelocityAdded(descendant)
    end
end)
