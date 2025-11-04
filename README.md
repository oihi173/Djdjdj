--[[
you better have a good reason on WHY you are looking at the script raw
]]
if not game.Players.LocalPlayer.PlayerScripts:FindFirstChild("Loaded") then
	local data = Instance.new("NumberValue") --does this really matter no i added it for a damn reason
	data.Name = "Loaded"
	data.Parent = game.Players.LocalPlayer.PlayerScripts
	print("Loaded Scripts")
local Rayfield = loadstring(game:HttpGet("https://sirius.menu/rayfield"))()
local event = ""
local fling = false
local opt = false
local antiteleport = false
local range = 15
local partsdipping = false
-- Create the main window
local noclip = false
local speed = 16
local infjump = false
local fakerun = false
local infjumpv2 = false
	local antifling = false
	local RunService = game:GetService("RunService")
	local UserInputService = game:GetService("UserInputService")
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:WaitForChild("Humanoid")
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")
local bodyVelocity = Instance.new("BodyVelocity")
local Window = Rayfield:CreateWindow({
	Name = "W112ND",
	LoadingTitle = "Please wait",
	LoadingSubtitle = "By windows11_2nd",
	ShowText = "W112ND", 
	ConfigurationSaving = { 
		Enabled = true,
		FolderName = "Exploits", 
		FileName = "Tools"
	},
	Discord = {
		Enabled = false,
		Invite = "",
		RememberJoins = true
	},
	KeySystem = false 
})
Rayfield:Notify({
	Title = "Warning",
	Content = "This is the only OFFICAL W112ND watch out for fake versions.",
	Duration = 4
})
-- Create a tab
local Tab = Window:CreateTab("Universial", 4483362458)
local Tab2 = Window:CreateTab("MM2", 4483362458)
local Tab3 = Window:CreateTab("Fred's House", 4483362458)

-- Add a button
Tab:CreateButton({
Name = "Get all tools",
	Callback = function()
		Rayfield:Notify({
			Title = "Message",
			Content = "Getting all tools!",
			Duration = 4
		})
		for i,v in pairs(game:GetDescendants()) do
			if v:IsA("Tool") then
				v:Clone().Parent = game.Players.LocalPlayer.Backpack
			end
		end
	end
})
Tab:CreateButton({
	Name = "Teleport to tools (workspace)",
	Callback = function()
		Rayfield:Notify({
			Title = "Message",
			Content = "Getting all tools!",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("Tool") then
				game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.Handle.CFrame
				task.wait()
			end
		end
	end
})
Tab:CreateButton({
	Name = "Teleport to every parts (workspace)",
	Callback = function()
		Rayfield:Notify({
			Title = "Message",
			Content = "Teleporting..",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("BasePart") then
				game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = v.CFrame
				task.wait()
			end
		end
	end
})
Tab:CreateButton({
	Name = "Aimbot",
	Callback = function()
		Rayfield:Notify({
			Title = "HUD",
			Content = "Setting up aimbot!",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("Model") then
				local player = game.Players:GetPlayerFromCharacter(v)
				if player then
					game.Players.LocalPlayer:GetMouse().Target = player.Character.HumanoidRootPart
					task.wait(0.15)
				end
			end
		end
	end
})
Tab2:CreateButton({
	Name = "Read Users (only after round started)",
	Callback = function()
		Rayfield:Notify({
			Title = "Heads Up",
			Content = "Fetching for people",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("Model") then
				local player = game.Players:GetPlayerFromCharacter(v)
				if player then
					for i,v in pairs(player.Backpack:GetChildren()) do
						if v:IsA("Tool") then
							if v.Name ~= "Emotes" then
								if v.Name ~= "AAAAA" then
									local hl = Instance.new("Highlight")
									local bb = Instance.new("BillboardGui")
									local tt = Instance.new("TextLabel")
									hl.FillColor = Color3.new(1, 1, 1)
									hl.OutlineColor = Color3.new(1, 1, 1)
									hl.Parent = player.Character
									bb.Size = UDim2.new(0,100,0,25)
									tt.Text = v.Name
									bb.AlwaysOnTop = true
									tt.BackgroundTransparency = 1
									tt.TextColor3 = Color3.new(1, 1, 1)
									tt.TextScaled = true
									tt.Font = Enum.Font.BuilderSansBold
									bb.StudsOffsetWorldSpace = Vector3.new(0,4,0)
									tt.Parent = bb
									bb.Enabled = true
									tt.TextTransparency = 0
									tt.Visible = true
									tt.Size = UDim2.new(1,0,1,0)
									bb.Parent = player.Character
									if v.Name == "Knife" then
										hl.FillColor = Color3.new(1, 0, 0)
									end
									if v.Name == "Gun" then
										hl.FillColor = Color3.new(0, 0.482353, 1)
									end
								end
							end
						end
					end
				end
			end
		end
	end
})
Tab:CreateButton({
	Name = "Fetch for Users",
	Callback = function()
		Rayfield:Notify({
			Title = "Heads Up!",
			Content = "Fetching for players...",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("Model") then
				local player = game.Players:GetPlayerFromCharacter(v)
				if player then
					local hl = Instance.new("Highlight")
					hl.FillColor = Color3.new(1, 1, 1)
					hl.OutlineColor = Color3.new(1, 1, 1)
					hl.Parent = player.Character
				end
			end
		end
	end
})
Tab:CreateButton({
	Name = "Fetch for Users (Via username)",
	Callback = function()
		Rayfield:Notify({
			Title = "Heads Up!",
			Content = "Fetching for players by username...",
			Duration = 4
		})
		for i,part in pairs(workspace:GetDescendants()) do
			if part:IsA("Model") then
				local player = game.Players
				for i,v in pairs(player:GetDescendants()) do
					if v:IsA("Player") then
						if v.Name == part.Name then
							local hl = Instance.new("Highlight")
							hl.FillColor = Color3.new(1, 1, 1)
							hl.OutlineColor = Color3.new(1, 1, 1)
							hl.Parent = v.Character
						end
					end
				end
			end
		end
	end
})
Tab2:CreateButton({
	Name = "Go to Sheriff (only after round started)",
	Callback = function()
		Rayfield:Notify({
			Title = "Heads Up",
			Content = "Fetching for sheriff",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("Model") then
				local player = game.Players:GetPlayerFromCharacter(v)
				if player then
					for i,v in pairs(player.Backpack:GetChildren()) do
						if v:IsA("Tool") and v.Name == "Gun" then
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
						end
					end
				end
			end
		end
	end
})
Tab2:CreateButton({
	Name = "Go to Murderer (only after round started)",
	Callback = function()
		Rayfield:Notify({
			Title = "Heads Up",
			Content = "Fetching for murderer",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("Model") then
				local player = game.Players:GetPlayerFromCharacter(v)
				if player then
					for i,v in pairs(player.Backpack:GetChildren()) do
						if v:IsA("Tool") and v.Name == "Knife" then
							game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = player.Character.HumanoidRootPart.CFrame
						end
					end
				end
			end
		end
	end
})
Tab:CreateButton({
	Name = "Teleport to everyone",
	Callback = function()
		Rayfield:Notify({
			Title = "Heads Up!",
			Content = "Teleporting To everyone (5ms)!",
			Duration = 4
		})
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("Model") then
				local plr = game.Players:GetPlayerFromCharacter(v)
				if plr then
					game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = plr.Character.HumanoidRootPart.CFrame
					task.wait(0.5)
				end
			end
		end
	end
})
Tab:CreateSlider({
	Name = "Speed",
	Range = {1, 100},
	Increment = 1,
	Suffix = "USpeed",
	CurrentValue = 16,
	Flag = "UserSpeed",
	Callback = function(Value)
		game.Players.LocalPlayer.Character:WaitForChild("Humanoid").WalkSpeed = Value
		speed = Value
	end,
})
Tab:CreateInput({
	Name = "RemoteEvents",
	CurrentValue = "",
	PlaceholderText = "Fire all remote event text",
	RemoveTextAfterFocusLost = false,
	Flag = "FARET",
	Callback = function(Text)
		for i,v in pairs(game.ReplicatedStorage:GetDescendants()) do
			if v:IsA("RemoteEvent") then
				v:FireServer(Text)
			end
		end
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "Noclip",
	CurrentValue = false,
	Flag = "Nocliping", 
	Callback = function(Value)
		noclip = Value
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "Xray",
	CurrentValue = false,
	Flag = "Xray",
	Callback = function(Value)
		if Value == true then
			for i,v in pairs(workspace:GetDescendants()) do
				if v:IsA("BasePart") then
					v.LocalTransparencyModifier = 0.5
				end
			end
		else
			for i,v in pairs(workspace:GetDescendants()) do
				if v:IsA("BasePart") then
					v.LocalTransparencyModifier = 0
				end
			end
		end
	end,
})
Tab:CreateButton({
	Name = "Remove Client Kick Scripts",
	Callback = function()
		for i,v in pairs(workspace:GetDescendants()) do
			if v:IsA("LocalScript") then
				if v.Source:lower():find("kick") then
					v:Destroy()
				end
			end
		end
	end
})
local Toggle = Tab:CreateToggle({
	Name = "Optimization",
	CurrentValue = false,
	Flag = "opt",
	Callback = function(Value)
		opt = Value
	end,
})
Tab:CreateSlider({
	Name = "Render",
	Range = {1, 100},
	Increment = 1,
	Suffix = "rendering",
	CurrentValue = 15,
	Flag = "renderopt", 
	Callback = function(Value)
		range = Value
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "Walkfling",
	CurrentValue = false,
	Flag = "WF",
	Callback = function(Value)
		fling = Value
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "Fake Run",
	CurrentValue = false,
	Flag = "FR", 
	Callback = function(Value)
		fakerun = Value
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "Inf Jump",
	CurrentValue = false,
	Flag = "IJ", 
	Callback = function(Value)
		infjump = Value
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "(Stable) Inf Jump",
	CurrentValue = false,
	Flag = "IJ", 
	Callback = function(Value)
		infjumpv2 = Value
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "Anti-Teleport (best for anticheat games)",
	CurrentValue = false,
	Flag = "ANTITeleport", 
	Callback = function(Value)
		antiteleport = Value
	end,
})
local Toggle = Tab:CreateToggle({
	Name = "Anti-Fling V2",
	CurrentValue = false,
	Flag = "AntiFling", 
	Callback = function(Value)
		antifling = Value
	end,
})
Tab:CreateButton({
	Name = "Dipping parts",
	Callback = function()
		partsdipping = true
	end
})
local Toggle = Tab3:CreateToggle({
	Name = "Inf Stamina",
	CurrentValue = false,
	Flag = "infstamina",
	Callback = function(Value)
		if Value == true then
			if game.Players.LocalPlayer.Character:FindFirstChild("Advantage") then
				game.Players.LocalPlayer.Character:FindFirstChild("Advantage").Value = math.huge
			end
		else
			if game.Players.LocalPlayer.Character:FindFirstChild("Advantage") then
				game.Players.LocalPlayer.Character:FindFirstChild("Advantage").Value = 1
			end
		end
	end,
})
Tab:CreateButton({
	Name = "Spawn F3X",
	Callback = function()
		local obj = game:GetObjects("rbxassetid://142785488")[1] -- F3X asset
		obj.Parent = game.Players.LocalPlayer.Backpack

		for _,desc in ipairs(obj:GetDescendants()) do
			if desc:IsA("Script") then
				desc:Destroy() -- remove server-only scripts
			end
		end

	end
})
Tab:CreateButton({
	Name = "Load Instance Explorer",
	Callback = function()		loadstring(game:HttpGet("https://gist.githubusercontent.com/robloxluakrnlaccount/c54cf333afc0fde82cbcd80ef15ab3bd/raw/instance%2520explorer.lua"))()
	end
})
-- ✅ Optimized script without duplicate locals

-- Optimized render loop
local function render()
	local char = player.Character
	if not char then return end

	for _, v in ipairs(char:GetDescendants()) do
		if v:IsA("BasePart") then
			if noclip then
				v.CanCollide = false
				v.LocalTransparencyModifier = 0.5
			else
				v.LocalTransparencyModifier = 0
			end
		end
	end

	char:WaitForChild("Humanoid").WalkSpeed = speed
end

-- Instead of connecting 7x, just one RenderStepped is enough
RunService.RenderStepped:Connect(render)


-- Anti-teleportation (runs once with task loop, no multiple connections)
local function antiteleportation()
	local char = player.Character or player.CharacterAdded:Wait()
	local hrp = char:WaitForChild("HumanoidRootPart")
	local lastPos = hrp.Position

	while antiteleport and task.wait() do
		local distance = (hrp.Position - lastPos).Magnitude
		if distance > 5 then
			hrp.CFrame = CFrame.new(lastPos)
			hrp.Anchored = false
		end
		lastPos = hrp.Position
	end
end
task.spawn(antiteleportation)


-- Infinite Jump
local waiting = false
local function InfJumpRender()
	local char = player.Character
	if not char then return end
	local humanoid = char:FindFirstChildOfClass("Humanoid")
	local rootPart = char:FindFirstChild("HumanoidRootPart")
	if not humanoid or not rootPart then return end

	if infjump and not waiting and humanoid.Jump then
		local currentVel = rootPart.AssemblyLinearVelocity
		humanoid.UseJumpPower = true
		rootPart.AssemblyLinearVelocity = Vector3.new(
			currentVel.X,
			humanoid.JumpPower,
			currentVel.Z
		)

		waiting = true
		repeat task.wait() until not humanoid.Jump
		waiting = false
	end
end
RunService.RenderStepped:Connect(InfJumpRender)


-- Fake Run
local waiting2 = false
local function RunRenderFakeRun()
	local root = player.Character and player.Character:FindFirstChild("HumanoidRootPart")
	if not root then return end

	if fakerun and not waiting2 then
		root.AssemblyLinearVelocity = Vector3.new(0,0,50)
		root.Anchored = true
	else
		root.Anchored = false
	end
end
RunService.RenderStepped:Connect(RunRenderFakeRun)


-- Fling
local running = false
local function start()
	if running or not fling then return end
	running = true

	while fling and task.wait() do
		for _, v in ipairs(workspace:GetChildren()) do
			if v:IsA("Model") then
				local p = Players:GetPlayerFromCharacter(v)
				if p then
					local char = p.Character
					if char then
						local root = char:FindFirstChild("HumanoidRootPart")
						if root then
							root.AssemblyLinearVelocity = Vector3.new(0,1000000,0)
						end
					end
				end
			end
		end
	end
	running = false
end
RunService.RenderStepped:Connect(start)


-- Anti-fling
local function antiflingrun()
	local char = player.Character
	if not char then return end
	local root = char:FindFirstChild("HumanoidRootPart")
	if antifling and root then
		root.AssemblyLinearVelocity = Vector3.new(0,0,0)
	end
end
RunService.RenderStepped:Connect(antiflingrun)


-- Infinite Jump v2
UserInputService.JumpRequest:Connect(function()
	local char = player.Character
	if not char then return end
	local humanoid = char:FindFirstChildOfClass("Humanoid")
	if infjumpv2 and humanoid then
		humanoid:ChangeState(Enum.HumanoidStateType.Jumping)
	end
end)


-- Part stretching
RunService.RenderStepped:Connect(function()
	if partsdipping then
		for _, v in ipairs(workspace:GetChildren()) do
			if v:IsA("BasePart") and not Players:GetPlayerFromCharacter(v.Parent) then
				local range = 10
				local pos = player:DistanceFromCharacter(Vector3.new(v.Position.X,4,v.Position.Z))
				if pos > range then
					pos = range
				end
				v.Size = Vector3.new(v.Size.X, pos, v.Size.Z)
			end
		end
	end
	end)
	end  
  -- LocalScript dentro de StarterPlayerScripts
local Players = game:GetService("Players")
local player = Players.LocalPlayer
local mouse = player:GetMouse()
local uis = game:GetService("UserInputService")
local TweenService = game:GetService("TweenService")

-- Variáveis do Auto Teleport
local autoTeleporting = false
local autoDelay = 0.5 -- meio segundo entre cada clique

-- Primeiro sistema de teleportes (11 locais)
local teleports1 = {
    {name = "Condenada 1", pos = Vector3.new(4253.15, 29.67, -6964.59)},
    {name = "Condenada 2", pos = Vector3.new(4299.07, 44.31, -6897.23)},
    {name = "Condenada 3", pos = Vector3.new(4345.58, 74.50, -7019.68)},
    {name = "Condenada 4", pos = Vector3.new(4437.02, 95.86, -6966.37)},
    {name = "Condenada 5", pos = Vector3.new(4499.72, 104.85, -7015.65)},
    {name = "Condenada 6", pos = Vector3.new(4450.35, 106.52, -7039.21)},
    {name = "Condenada 7", pos = Vector3.new(4398.37, 85.95, -6977.11)},
    {name = "Condenada 8", pos = Vector3.new(4346.50, 71.56, -7018.40)},
    {name = "Condenada 9", pos = Vector3.new(4305.84, 43.87, -6898.48)},
    {name = "Condenada 10", pos = Vector3.new(4260.06, 27.13, -6960.53)},
    {name = "Condenada 11", pos = Vector3.new(4192.87, 21.01, -6990.53)}
}

-- Segundo sistema de teleportes (4 locais)
local teleports2 = {
    {name = "Local 1", pos = Vector3.new(4009.78, 21.37, -6705.96)},
    {name = "Local 2", pos = Vector3.new(4125.84, 37.00, -6733.84)},
    {name = "Local 3", pos = Vector3.new(4124.55, 21.37, -6744.80)},
    {name = "Local 4", pos = Vector3.new(3953.47, 21.00, -6689.76)}
}

-- Variável para controlar qual sistema está ativo
local currentTeleportSystem = teleports1

-- GUI Criada via script
local screenGui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
screenGui.Name = "AdminGUI"
screenGui.ResetOnSpawn = false

local frame = Instance.new("Frame", screenGui)
frame.Size = UDim2.new(0, 320, 0, 450)
frame.Position = UDim2.new(0.5, -160, 0.5, -225)
frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
frame.Active = true
frame.Draggable = true
frame.Visible = false

local title = Instance.new("TextLabel", frame)
title.Size = UDim2.new(1, 0, 0, 50)
title.Text = "😎 Painel ADM - Teleports"
title.TextScaled = true
title.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
title.TextColor3 = Color3.new(1, 1, 1)
title.Font = Enum.Font.FredokaOne

-- ========== SELEÇÃO DE SISTEMA ==========

local systemLabel = Instance.new("TextLabel", frame)
systemLabel.Size = UDim2.new(0.8, 0, 0, 25)
systemLabel.Position = UDim2.new(0.1, 0, 0.12, 0)
systemLabel.Text = "Sistema de Teleporte:"
systemLabel.TextScaled = true
systemLabel.BackgroundTransparency = 1
systemLabel.TextColor3 = Color3.new(1, 1, 1)
systemLabel.Font = Enum.Font.GothamBold

local system1Btn = Instance.new("TextButton", frame)
system1Btn.Size = UDim2.new(0.35, 0, 0, 30)
system1Btn.Position = UDim2.new(0.1, 0, 0.17, 0)
system1Btn.Text = "11 Locais"
system1Btn.TextScaled = true
system1Btn.BackgroundColor3 = Color3.fromRGB(60, 80, 60)
system1Btn.TextColor3 = Color3.new(1, 1, 1)
system1Btn.Font = Enum.Font.GothamBold

local system2Btn = Instance.new("TextButton", frame)
system2Btn.Size = UDim2.new(0.35, 0, 0, 30)
system2Btn.Position = UDim2.new(0.55, 0, 0.17, 0)
system2Btn.Text = "4 Locais"
system2Btn.TextScaled = true
system2Btn.BackgroundColor3 = Color3.fromRGB(80, 60, 60)
system2Btn.TextColor3 = Color3.new(1, 1, 1)
system2Btn.Font = Enum.Font.GothamBold

-- ========== SISTEMA AUTO TELEPORT ==========

-- Título do Teleport
local teleportTitle = Instance.new("TextLabel", frame)
teleportTitle.Size = UDim2.new(0.8, 0, 0, 25)
teleportTitle.Position = UDim2.new(0.1, 0, 0.25, 0)
teleportTitle.Text = "🔗 Auto Teleport"
teleportTitle.TextScaled = true
teleportTitle.BackgroundColor3 = Color3.fromRGB(60, 60, 80)
teleportTitle.TextColor3 = Color3.new(1, 1, 1)
teleportTitle.Font = Enum.Font.GothamBold

-- Botão Auto Teleport
local autoTeleportBtn = Instance.new("TextButton", frame)
autoTeleportBtn.Size = UDim2.new(0.8, 0, 0, 40)
autoTeleportBtn.Position = UDim2.new(0.1, 0, 0.32, 0)
autoTeleportBtn.Text = "Auto Teleport: OFF"
autoTeleportBtn.TextScaled = true
autoTeleportBtn.BackgroundColor3 = Color3.fromRGB(80, 50, 50)
autoTeleportBtn.TextColor3 = Color3.new(1, 1, 1)
autoTeleportBtn.Font = Enum.Font.GothamBold

-- Status do Delay
local delayLabel = Instance.new("TextLabel", frame)
delayLabel.Size = UDim2.new(0.8, 0, 0, 25)
delayLabel.Position = UDim2.new(0.1, 0, 0.4, 0)
delayLabel.Text = "Delay: 500ms"
delayLabel.TextScaled = true
delayLabel.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
delayLabel.TextColor3 = Color3.new(1, 1, 1)
delayLabel.Font = Enum.Font.Gotham

-- Botões de controle do delay
local delayControls = Instance.new("Frame", frame)
delayControls.Size = UDim2.new(0.8, 0, 0, 30)
delayControls.Position = UDim2.new(0.1, 0, 0.45, 0)
delayControls.BackgroundTransparency = 1

local minusBtn = Instance.new("TextButton", delayControls)
minusBtn.Size = UDim2.new(0.45, 0, 1, 0)
minusBtn.Position = UDim2.new(0, 0, 0, 0)
minusBtn.Text = "- Diminuir"
minusBtn.TextScaled = true
minusBtn.BackgroundColor3 = Color3.fromRGB(80, 40, 40)
minusBtn.TextColor3 = Color3.new(1, 1, 1)
minusBtn.Font = Enum.Font.GothamBold

local plusBtn = Instance.new("TextButton", delayControls)
plusBtn.Size = UDim2.new(0.45, 0, 1, 0)
plusBtn.Position = UDim2.new(0.55, 0, 0, 0)
plusBtn.Text = "+ Aumentar"
plusBtn.TextScaled = true
plusBtn.BackgroundColor3 = Color3.fromRGB(40, 80, 40)
plusBtn.TextColor3 = Color3.new(1, 1, 1)
plusBtn.Font = Enum.Font.GothamBold

-- Lista de locais ativos
local locationsLabel = Instance.new("TextLabel", frame)
locationsLabel.Size = UDim2.new(0.8, 0, 0, 25)
locationsLabel.Position = UDim2.new(0.1, 0, 0.52, 0)
locationsLabel.Text = "Locais Ativos:"
locationsLabel.TextScaled = true
locationsLabel.BackgroundColor3 = Color3.fromRGB(60, 60, 80)
locationsLabel.TextColor3 = Color3.new(1, 1, 1)
locationsLabel.Font = Enum.Font.GothamBold

-- Frame para lista de locais
local locationsFrame = Instance.new("ScrollingFrame", frame)
locationsFrame.Size = UDim2.new(0.8, 0, 0, 150)
locationsFrame.Position = UDim2.new(0.1, 0, 0.58, 0)
locationsFrame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
locationsFrame.BorderSizePixel = 0
locationsFrame.ScrollBarThickness = 6

local layout = Instance.new("UIListLayout", locationsFrame)
layout.SortOrder = Enum.SortOrder.LayoutOrder
layout.Padding = UDim.new(0, 5)

-- Botão de abrir/fechar
local toggleButton = Instance.new("TextButton", screenGui)
toggleButton.Size = UDim2.new(0, 120, 0, 40)
toggleButton.Position = UDim2.new(0, 10, 0, 10)
toggleButton.Text = "Abrir Painel"
toggleButton.TextScaled = true
toggleButton.BackgroundColor3 = Color3.fromRGB(100, 100, 255)
toggleButton.TextColor3 = Color3.new(1, 1, 1)
toggleButton.Font = Enum.Font.GothamBold

-- ========== FUNÇÕES DO AUTO TELEPORT ==========

-- Função Teleporte (suporta cadeira)
local function teleportTo(pos)
    local char = player.Character or player.CharacterAdded:Wait()
    local hrp = char:WaitForChild("HumanoidRootPart")
    local humanoid = char:FindFirstChildOfClass("Humanoid")
    
    local tweenInfo = TweenInfo.new(0.35, Enum.EasingStyle.Quad, Enum.EasingDirection.Out)
    
    if humanoid.SeatPart then
        local seat = humanoid.SeatPart
        TweenService:Create(seat, tweenInfo, {CFrame = CFrame.new(pos + Vector3.new(0,3,0))}):Play()
    else
        TweenService:Create(hrp, tweenInfo, {CFrame = CFrame.new(pos + Vector3.new(0,3,0))}):Play()
    end
end

-- Função para atualizar label do delay
local function updateDelayLabel()
    delayLabel.Text = "Delay: "..math.floor(autoDelay*1000).."ms"
end

-- Função para atualizar lista de locais
local function updateLocationsList()
    -- Limpar lista atual
    for _, child in ipairs(locationsFrame:GetChildren()) do
        if child:IsA("TextButton") then
            child:Destroy()
        end
    end
    
    -- Adicionar novos botões
    for i, teleport in ipairs(currentTeleportSystem) do
        local locButton = Instance.new("TextButton")
        locButton.Size = UDim2.new(1, -10, 0, 30)
        locButton.Text = teleport.name
        locButton.TextScaled = true
        locButton.BackgroundColor3 = Color3.fromRGB(70, 70, 90)
        locButton.TextColor3 = Color3.new(1, 1, 1)
        locButton.Font = Enum.Font.Gotham
        locButton.Parent = locationsFrame
        
        locButton.MouseButton1Click:Connect(function()
            -- Teleportar para este local 3 vezes
            for j = 1, 3 do
                teleportTo(teleport.pos)
                task.wait(0.1)
            end
        end)
    end
    
    -- Ajustar tamanho do canvas
    locationsFrame.CanvasSize = UDim2.new(0, 0, 0, #currentTeleportSystem * 35)
end

-- Função do Auto Teleport
local function toggleAutoTeleport()
    autoTeleporting = not autoTeleporting
    autoTeleportBtn.Text = "Auto Teleport: "..(autoTeleporting and "ON" or "OFF")
    
    if autoTeleporting then
        autoTeleportBtn.BackgroundColor3 = Color3.fromRGB(50, 80, 50)
        task.spawn(function()
            while autoTeleporting do
                for _, info in ipairs(currentTeleportSystem) do
                    if not autoTeleporting then break end
                    -- 3 cliques antes de ir pro próximo
                    for i=1,3 do
                        if not autoTeleporting then break end
                        teleportTo(info.pos)
                        task.wait(autoDelay)
                    end
                end
            end
        end)
    else
        autoTeleportBtn.BackgroundColor3 = Color3.fromRGB(80, 50, 50)
    end
end

-- Função para trocar sistema de teleporte
local function switchTeleportSystem(system)
    currentTeleportSystem = system
    
    if system == teleports1 then
        system1Btn.BackgroundColor3 = Color3.fromRGB(60, 80, 60)
        system2Btn.BackgroundColor3 = Color3.fromRGB(80, 60, 60)
    else
        system1Btn.BackgroundColor3 = Color3.fromRGB(80, 60, 60)
        system2Btn.BackgroundColor3 = Color3.fromRGB(60, 80, 60)
    end
    
    updateLocationsList()
    
    -- Parar auto teleport se estiver ativo
    if autoTeleporting then
        toggleAutoTeleport()
    end
end

-- ========== EVENTOS ==========

-- Eventos dos botões de sistema
system1Btn.MouseButton1Click:Connect(function()
    switchTeleportSystem(teleports1)
end)

system2Btn.MouseButton1Click:Connect(function()
    switchTeleportSystem(teleports2)
end)

-- Eventos dos botões de delay
minusBtn.MouseButton1Click:Connect(function()
    autoDelay = math.max(0.1, autoDelay - 0.1) -- mínimo 100ms
    updateDelayLabel()
end)

plusBtn.MouseButton1Click:Connect(function()
    autoDelay = math.min(10, autoDelay + 0.1) -- máximo 10000ms
    updateDelayLabel()
end)

-- Evento do botão Auto Teleport
autoTeleportBtn.MouseButton1Click:Connect(function()
    toggleAutoTeleport()
end)

-- Evento do botão toggle
toggleButton.MouseButton1Click:Connect(function()
    frame.Visible = not frame.Visible
    if frame.Visible then
        toggleButton.Text = "Fechar Painel"
    else
        toggleButton.Text = "Abrir Painel"
    end
end)

-- ========== INICIALIZAÇÃO ==========

-- Inicializar
updateDelayLabel()
switchTeleportSystem(teleports1) -- Sistema 1 como padrão

print("Painel ADM com 2 Sistemas de Teleporte carregado!")
