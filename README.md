-- Criando a interface gráfica
local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local UICornerMainFrame = Instance.new("UICorner")
local Title = Instance.new("TextLabel")
local ButtonGetMoney = Instance.new("TextButton")
local UICornerButton = Instance.new("UICorner")

-- Configurações do ScreenGui
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

-- Configurações do MainFrame
MainFrame.Parent = ScreenGui
MainFrame.BackgroundColor3 = Color3.fromRGB(230, 50, 50) -- Cor inspirada na interface da imagem
MainFrame.Size = UDim2.new(0, 350, 0, 200)
MainFrame.Position = UDim2.new(0.5, -175, 0.5, -100)
MainFrame.Active = true
MainFrame.Draggable = true

-- Cantos arredondados para o MainFrame
UICornerMainFrame.CornerRadius = UDim.new(0, 15)
UICornerMainFrame.Parent = MainFrame

-- Configurações do título
Title.Parent = MainFrame
Title.Text = "tubergamer(beta)(1.2)"
Title.Size = UDim2.new(1, 0, 0, 50)
Title.BackgroundColor3 = Color3.fromRGB(200, 30, 30) -- Destaque para o cabeçalho
Title.TextColor3 = Color3.fromRGB(255, 255, 255)
Title.Font = Enum.Font.SourceSansBold
Title.TextSize = 20

-- Configurações do botão "get money (new)"
ButtonGetMoney.Parent = MainFrame
ButtonGetMoney.Text = "get money (new)"
ButtonGetMoney.Size = UDim2.new(0, 300, 0, 50)
ButtonGetMoney.Position = UDim2.new(0.5, -150, 0.6, -25)
ButtonGetMoney.BackgroundColor3 = Color3.fromRGB(50, 200, 100)
ButtonGetMoney.TextColor3 = Color3.fromRGB(255, 255, 255)
ButtonGetMoney.Font = Enum.Font.SourceSansBold
ButtonGetMoney.TextSize = 18

-- Cantos arredondados para o botão
UICornerButton.CornerRadius = UDim.new(0, 10)
UICornerButton.Parent = ButtonGetMoney

-- Adicionando funcionalidade ao botão "get money (new)"
ButtonGetMoney.MouseButton1Click:Connect(function()
    local rs = game:GetService("ReplicatedStorage")

    local args = {
        [1] = {
            [1] = "Getting Settled",
            [2] = {
                [1] = {
                    [1] = 0,
                    [2] = 0
                },
                [2] = "Any"
            },
            [3] = {
                [1] = 9e9 -- Valor de dinheiro e XP
            },
            [4] = "Found by @kylosilly on discord <3"
        }
    }

    rs:WaitForChild("Give_Quest"):FireServer(unpack(args))
    rs:WaitForChild("Win_Quest"):FireServer("Getting Settled")
end)
