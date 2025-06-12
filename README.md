local KeySystem = {}

function KeySystem.WaitForValidation()
    local validated = false
    local gui = Instance.new("ScreenGui")
    gui.Name = "AkatsukiHub"
    gui.ResetOnSpawn = false
    gui.IgnoreGuiInset = true
    gui.Parent = game:GetService("CoreGui")

    local mainFrame = Instance.new("Frame")
    mainFrame.Size = UDim2.new(0, 400, 0, 200)
    mainFrame.Position = UDim2.new(0.5, 0, 0.5, 0)
    mainFrame.AnchorPoint = Vector2.new(0.5, 0.5)
    mainFrame.BackgroundColor3 = Color3.fromRGB(15, 15, 15)
    mainFrame.BorderSizePixel = 0
    mainFrame.Parent = gui

    local function applyCornerRadius(instance, radius)
        local corner = Instance.new("UICorner")
        corner.CornerRadius = UDim.new(0, radius)
        corner.Parent = instance
        return corner
    end
    applyCornerRadius(mainFrame, 8)

    local label = Instance.new("TextLabel")
    label.Text = "Click to enter without key"
    label.Size = UDim2.new(1, 0, 0.4, 0)
    label.Position = UDim2.new(0, 0, 0.1, 0)
    label.BackgroundTransparency = 1
    label.TextColor3 = Color3.fromRGB(255, 255, 255)
    label.TextSize = 18
    label.Font = Enum.Font.GothamBold
    label.Parent = mainFrame

    local button = Instance.new("TextButton")
    button.Text = "ENTER WITHOUT KEY"
    button.Size = UDim2.new(0.6, 0, 0, 40)
    button.Position = UDim2.new(0.2, 0, 0.6, 0)
    button.BackgroundColor3 = Color3.fromRGB(200, 0, 0)
    button.TextColor3 = Color3.fromRGB(255, 255, 255)
    button.Font = Enum.Font.GothamBlack
    button.TextSize = 16
    applyCornerRadius(button, 6)
    button.Parent = mainFrame

    button.MouseButton1Click:Connect(function()
        validated = true
        gui:Destroy()
    end)

    repeat task.wait() until validated
    return true
end

return KeySystem
