-- Carregar a biblioteca Rayfield
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

-- Criar a janela principal
local Window = Rayfield:CreateWindow({
    Name = "Brookhaven Script Hub 🏡",
    LoadingTitle = "Carregando...",
    LoadingSubtitle = "Por SeuNome",
    ConfigurationSaving = {
        Enabled = true,
        FolderName = nil,
        FileName = "BrookhavenHub"
    },
    Discord = {
        Enabled = false,
        Invite = "",
        RememberJoins = true
    },
    KeySystem = false,
    KeySettings = {
        Title = "Brookhaven Script Hub",
        Subtitle = "Sistema de Chave",
        Note = "Insira sua chave",
        FileName = "Key",
        SaveKey = true,
        GrabKeyFromSite = false,
        Key = {"sua_chave_aqui"}
    }
})

-- Criar uma aba principal
local MainTab = Window:CreateTab("Principal", 4483362458)

-- Seção de Movimento
local MovementSection = MainTab:CreateSection("Movimento")

-- Noclip
local noclipEnabled = false
local noclipConnection

MainTab:CreateToggle({
    Name = "Noclip",
    CurrentValue = false,
    Callback = function(Value)
        noclipEnabled = Value
        if noclipEnabled then
            noclipConnection = game:GetService("RunService").Stepped:Connect(function()
                for _, part in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
                    if part:IsA("BasePart") then
                        part.CanCollide = false
                    end
                end
            end)
        else
            if noclipConnection then
                noclipConnection:Disconnect()
            end
            for _, part in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
                if part:IsA("BasePart") then
                    part.CanCollide = true
                end
            end
        end
    end,
})

-- Fly
MainTab:CreateButton({
    Name = "Ativar Fly (Pressione 'X' para alternar)",
    Callback = function()
        loadstring(game:HttpGet("https://pastebin.com/raw/6Y3Y8QY0"))()
    end,
})

-- ESP
MainTab:CreateButton({
    Name = "Ativar ESP",
    Callback = function()
        loadstring(game:HttpGet("https://pastebin.com/raw/0yJbYQY0"))()
    end,
})

-- Seção de Ajustes
local SettingsSection = MainTab:CreateSection("Ajustes")

-- Velocidade
MainTab:CreateSlider({
    Name = "Velocidade",
    Range = {16, 100},
    Increment = 1,
    Suffix = "Velocidade",
    CurrentValue = 16,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
    end,
})

-- Potência do Pulo
MainTab:CreateSlider({
    Name = "Potência do Pulo",
    Range = {50, 150},
    Increment = 1,
    Suffix = "Potência",
    CurrentValue = 50,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
    end,
})

-- Pulo Infinito
local infiniteJumpEnabled = false

MainTab:CreateToggle({
    Name = "Pulo Infinito",
    CurrentValue = false,
    Callback = function(Value)
        infiniteJumpEnabled = Value
        if infiniteJumpEnabled then
            game:GetService("UserInputService").JumpRequest:Connect(function()
                if infiniteJumpEnabled then
                    game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid"):ChangeState("Jumping")
                end
            end)
        end
    end,
})-- Carregar a biblioteca Rayfield
local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()

-- Criar a janela principal
local Window = Rayfield:CreateWindow({
    Name = "Brookhaven Script Hub 🏡",
    LoadingTitle = "Carregando...",
    LoadingSubtitle = "Por SeuNome",
    ConfigurationSaving = {
        Enabled = true,
        FolderName = nil,
        FileName = "BrookhavenHub"
    },
    Discord = {
        Enabled = false,
        Invite = "",
        RememberJoins = true
    },
    KeySystem = false,
    KeySettings = {
        Title = "Brookhaven Script Hub",
        Subtitle = "Sistema de Chave",
        Note = "Insira sua chave",
        FileName = "Key",
        SaveKey = true,
        GrabKeyFromSite = false,
        Key = {"sua_chave_aqui"}
    }
})

-- Criar uma aba principal
local MainTab = Window:CreateTab("Principal", 4483362458)

-- Seção de Movimento
local MovementSection = MainTab:CreateSection("Movimento")

-- Noclip
local noclipEnabled = false
local noclipConnection

MainTab:CreateToggle({
    Name = "Noclip",
    CurrentValue = false,
    Callback = function(Value)
        noclipEnabled = Value
        if noclipEnabled then
            noclipConnection = game:GetService("RunService").Stepped:Connect(function()
                for _, part in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
                    if part:IsA("BasePart") then
                        part.CanCollide = false
                    end
                end
            end)
        else
            if noclipConnection then
                noclipConnection:Disconnect()
            end
            for _, part in pairs(game.Players.LocalPlayer.Character:GetDescendants()) do
                if part:IsA("BasePart") then
                    part.CanCollide = true
                end
            end
        end
    end,
})

-- Fly
MainTab:CreateButton({
    Name = "Ativar Fly (Pressione 'X' para alternar)",
    Callback = function()
        loadstring(game:HttpGet("https://pastebin.com/raw/6Y3Y8QY0"))()
    end,
})

-- ESP
MainTab:CreateButton({
    Name = "Ativar ESP",
    Callback = function()
        loadstring(game:HttpGet("https://pastebin.com/raw/0yJbYQY0"))()
    end,
})

-- Seção de Ajustes
local SettingsSection = MainTab:CreateSection("Ajustes")

-- Velocidade
MainTab:CreateSlider({
    Name = "Velocidade",
    Range = {16, 100},
    Increment = 1,
    Suffix = "Velocidade",
    CurrentValue = 16,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Value
    end,
})

-- Potência do Pulo
MainTab:CreateSlider({
    Name = "Potência do Pulo",
    Range = {50, 150},
    Increment = 1,
    Suffix = "Potência",
    CurrentValue = 50,
    Callback = function(Value)
        game.Players.LocalPlayer.Character.Humanoid.JumpPower = Value
    end,
})

-- Pulo Infinito
local infiniteJumpEnabled = false

MainTab:CreateToggle({
    Name = "Pulo Infinito",
    CurrentValue = false,
    Callback = function(Value)
        infiniteJumpEnabled = Value
        if infiniteJumpEnabled then
            game:GetService("UserInputService").JumpRequest:Connect(function()
                if infiniteJumpEnabled then
                    game.Players.LocalPlayer.Character:FindFirstChildOfClass("Humanoid"):ChangeState("Jumping")
                end
            end)
        end
    end,
})
