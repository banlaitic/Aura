--Banlaitic Robot--

local player = game.Players.LocalPlayer or game.Players.PlayerAdded:Wait()
local char = player.Character or player.CharacterAdded:Wait()
local button = script.Parent
local auraEvent = game.ReplicatedStorage.AuraEvent
local toggle = false
local userInputService = game:GetService("UserInputService")


userInputService.InputBegan:Connect(function(input, gameProcessed)
	if gameProcessed then return end

	if input.KeyCode == Enum.KeyCode.J then
		if not toggle then
			toggle = true
			auraEvent:FireServer(char)
		else
			toggle = false
			char.HumanoidRootPart.Effect:Destroy()
		end
	end
end)

--AURA--
