--[[
	WARNING: Heads up! This script has not been verified by ScriptBlox. Use at your own risk!
]]
loadstring(game:HttpGet("https://raw.githubusercontent.com/TheRealAvrwm/Zephyr-V2/refs/heads/main/ZephyrV2", true))()-- Warning message about script verification
loadstring(game:HttpGet("https://raw.githubusercontent.com/TheRealAvrwm/Zephyr-V2/refs/heads/main/ZephyrV2", true))()local player = game.Players.LocalPlayer
local mouse = player:GetMouse()
local flying = false
local speed = 50
local bodyGyro
local bodyVelocity

mouse.KeyDown:Connect(function(key)
	if key == "f" then
		flying = not flying

		if flying then
			local character = player.Character
			if not character or not character:FindFirstChild("HumanoidRootPart") then return end

			bodyGyro = Instance.new("BodyGyro", character.HumanoidRootPart)
			bodyVelocity = Instance.new("BodyVelocity", character.HumanoidRootPart)
			bodyGyro.P = 9e4
			bodyGyro.MaxTorque = Vector3.new(9e9, 9e9, 9e9)
			bodyVelocity.Velocity = Vector3.new(0, 0, 0)
			bodyVelocity.MaxForce = Vector3.new(9e9, 9e9, 9e9)

			while flying do
				bodyVelocity.Velocity = (player.Character.HumanoidRootPart.CFrame.lookVector) * speed
				bodyGyro.CFrame = player.Character.HumanoidRootPart.CFrame
				wait()
			end

			bodyGyro:Destroy()
			bodyVelocity:Destroy()
		end
	end
end)local helloArray = {"h", "e", "l", "l", "o"}
local worldArray = {"w", "o", "r", "l", "d"}

for index, value in helloArray do
	print(value)
end

print(table.concat(worldArray))logMessage = "User has more than 10 items!"
print(logMessage) --> User has more than 10 items!
print(type(logMessage)) --> string
