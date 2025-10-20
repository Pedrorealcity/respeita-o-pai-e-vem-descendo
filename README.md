# respeita-o-pai-e-vem-descendo-- Black Grimoire Script: Auto Farm, ESP de Player, Aimbot, Painel de Controle

-- Dependências
local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

-- Painel de Controle (GUI)
local ScreenGui = Instance.new("ScreenGui", game.CoreGui)
local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 300, 0, 300)
Frame.Position = UDim2.new(0, 100, 0, 100)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.BorderSizePixel = 0

local function createButton(name, pos, func)
    local btn = Instance.new("TextButton", Frame)
    btn.Text = name
    btn.Size = UDim2.new(0, 280, 0, 40)
    btn.Position = UDim2.new(0, 10, 0, pos)
    btn.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
    btn.MouseButton1Click:Connect(func)
end

-- ESP de Player
local espEnabled = false
function toggleESP()
    espEnabled = not espEnabled
    if espEnabled then
        for _, player in pairs(Players:GetPlayers()) do
            if player ~= LocalPlayer then
