
-- Script Hub de Auto Farm Level e Teleporte para Baús
-- Este script não é específico para nenhum jogo. Adapte conforme necessário.

local AutoFarmEnabled = false
local TeleportToChestsEnabled = false

-- Função para Auto Farm Level
local function AutoFarmLevel()
    while AutoFarmEnabled do
        -- Código de auto farm level aqui
        -- Exemplo: Atacar inimigos, coletar itens, completar missões, etc.
        
        print("Auto farming level...") -- Remova ou substitua por ações específicas
        wait(1) -- Intervalo entre ações (ajuste conforme necessário)
    end
end

-- Função para teleporte para baús
local function TeleportToChests()
    while TeleportToChestsEnabled do
        -- Código de teleporte para baús aqui
        -- Exemplo: Encontrar e teletransportar para a posição dos baús
        
        print("Teleporting to chest...") -- Remova ou substitua por ações específicas
        wait(5) -- Intervalo entre teleportes (ajuste conforme necessário)
    end
end

-- Interface do Usuário para habilitar/desabilitar Auto Farm e Teleporte
local function CreateUI()
    local ScreenGui = Instance.new("ScreenGui")
    local AutoFarmButton = Instance.new("TextButton")
    local TeleportButton = Instance.new("TextButton")
    
    ScreenGui.Parent = game.CoreGui
    
    -- Configuração do botão de Auto Farm
    AutoFarmButton.Size = UDim2.new(0, 200, 0, 50)
    AutoFarmButton.Position = UDim2.new(0, 50, 0, 50)
    AutoFarmButton.Text = "Toggle Auto Farm"
    AutoFarmButton.Parent = ScreenGui
    
    AutoFarmButton.MouseButton1Click:Connect(function()
        AutoFarmEnabled = not AutoFarmEnabled
        if AutoFarmEnabled then
            AutoFarmLevel()
        end
    end)
    
    -- Configuração do botão de Teleporte para Baús
    TeleportButton.Size = UDim2.new(0, 200, 0, 50)
    TeleportButton.Position = UDim2.new(0, 50, 0, 110)
    TeleportButton.Text = "Toggle Teleport to Chests"
    TeleportButton.Parent = ScreenGui
    
    TeleportButton.MouseButton1Click:Connect(function()
        TeleportToChestsEnabled = not TeleportToChestsEnabled
        if TeleportToChestsEnabled then
            TeleportToChests()
        end
    end)
end

-- Inicializa a interface do usuário
CreateUI()
