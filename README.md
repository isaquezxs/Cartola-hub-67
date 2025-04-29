# Cartola-hub-67
Hehejwjeje
-- Brookhaven Script HUB Simples (Exemplo)
-- Feito para uso com exploit executores como Synapse X, Fluxus, etc.

local Players = game:GetService("Players")
local LocalPlayer = Players.LocalPlayer

local function desbanirCasa()
    print("Você foi desbanido da casa!")
    -- Insira aqui o código para redefinir banimentos, se possível
end

local function pegarPermissao()
    print("Permissão da casa adquirida!")
    -- Código para burlar sistema de permissões, se viável
end

local function comprarCasa()
    print("Casa comprada automaticamente.")
    -- Código para comprar casa (simular clique ou acionar evento remoto)
end

-- GUI simples
local ScreenGui = Instance.new("ScreenGui", LocalPlayer.PlayerGui)
local Frame = Instance.new("Frame", ScreenGui)
Frame.Size = UDim2.new(0, 300, 0, 200)
Frame.Position = UDim2.new(0.5, -150, 0.5, -100)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)

local function criarBotao(nome, posY, acao)
    local btn = Instance.new("TextButton", Frame)
    btn.Size = UDim2.new(1, -20, 0, 40)
    btn.Position = UDim2.new(0, 10, 0, posY)
    btn.Text = nome
    btn.TextColor3 = Color3.new(1, 1, 1)
    btn.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
    btn.MouseButton1Click:Connect(acao)
end

criarBotao("Desbanir da Casa", 10, desbanirCasa)
criarBotao("Pegar Permissão", 60, pegarPermissao)
criarBotao("Comprar Casa", 110, comprarCasa)local boat = script.Parent

-- Cria um corpo de força
local bodyVelocity = Instance.new("BodyVelocity")
bodyVelocity.Velocity = Vector3.new(0, 100, 0) -- Joga o barco para cima
bodyVelocity.MaxForce = Vector3.new(1e6, 1e6, 1e6)
bodyVelocity.Parent = boat

-- Remove a força depois de 2 segundos
wait(2)
bodyVelocity:Destroy()
