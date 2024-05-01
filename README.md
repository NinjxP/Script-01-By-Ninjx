-- Script Por: Ninjx

-- Criação do menu
local menu = Instance.new("ScreenGui")
local frame = Instance.new("Frame")
local closeButton = Instance.new("TextButton")
local speedButton = Instance.new("TextButton")
local jumpButton = Instance.new("TextButton")
local titleLabel = Instance.new("TextLabel")

-- Configuração do menu
menu.Name = "Menu"
menu.Parent = game.CoreGui

frame.Name = "Frame"
frame.Parent = menu
frame.BackgroundColor3 = Color3.fromRGB(255, 255, 0)
frame.Position = UDim2.new(0.5, -100, 0.5, -100)
frame.Size = UDim2.new(0, 200, 0, 200)
frame.BorderSizePixel = 5
frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
frame.Active = true
frame.Draggable = true

-- Configuração do título
titleLabel.Name = "TitleLabel"
titleLabel.Parent = frame
titleLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 0)
titleLabel.Position = UDim2.new(0, 0, 0, 0)
titleLabel.Size = UDim2.new(1, 0, 0, 30)
titleLabel.Text = "By: Ninjx"
titleLabel.TextColor3 = Color3.fromRGB(0, 0, 0)

-- Configuração do botão de fechar
closeButton.Name = "CloseButton"
closeButton.Parent = frame
closeButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
closeButton.Position = UDim2.new(0.85, 0, 0, 0)
closeButton.Size = UDim2.new(0, 30, 0, 30)
closeButton.Text = "X"
closeButton.BorderSizePixel = 5
closeButton.BorderColor3 = Color3.fromRGB(0, 0, 0)

-- Configuração do botão de velocidade
speedButton.Name = "SpeedButton"
speedButton.Parent = frame
speedButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
speedButton.Position = UDim2.new(0.5, -50, 0.5, -25)
speedButton.Size = UDim2.new(0, 100, 0, 50)
speedButton.Text = "Speed"
speedButton.BorderSizePixel = 5
speedButton.BorderColor3 = Color3.fromRGB(0, 0, 0)

-- Configuração do botão de pulo
jumpButton.Name = "JumpButton"
jumpButton.Parent = frame
jumpButton.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
jumpButton.Position = UDim2.new(0.5, -50, 0.5, 30)
jumpButton.Size = UDim2.new(0, 100, 0, 50)
jumpButton.Text = "Jump"
jumpButton.BorderSizePixel = 5
jumpButton.BorderColor3 = Color3.fromRGB(0, 0, 0)

-- Variáveis para controle de velocidade e pulo
local speedEnabled = false
local jumpEnabled = false

-- Funções dos botões
local function closeMenu()
    menu.Enabled = false
end

local function toggleSpeed()
    speedEnabled = not speedEnabled
    local speed = speedEnabled and 50 or 16
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = speed
end

local function toggleJump()
    jumpEnabled = not jumpEnabled
    local jumpPower = jumpEnabled and 100 or 50
    game.Players.LocalPlayer.Character.Humanoid.JumpPower = jumpPower
end

-- Conectando as funções aos botões
closeButton.MouseButton1Click:Connect(closeMenu)
speedButton.MouseButton1Click:Connect(toggleSpeed)
jumpButton.MouseButton1Click:Connect(toggleJump)
