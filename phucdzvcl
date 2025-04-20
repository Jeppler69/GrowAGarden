-- Tạo GUI chính
local player = game.Players.LocalPlayer
local gui = Instance.new("ScreenGui", player:WaitForChild("PlayerGui"))
gui.Name = "GrowGui"

local frame = Instance.new("Frame", gui)
frame.Size = UDim2.new(0, 220, 0, 180)
frame.Position = UDim2.new(0, 20, 0, 200)
frame.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
frame.BorderSizePixel = 0
frame.Active = true
frame.Draggable = true

-- Tiêu đề
local title = Instance.new("TextLabel", frame)
title.Size = UDim2.new(1, 0, 0, 30)
title.BackgroundColor3 = Color3.fromRGB(25, 25, 25)
title.Text = "GROW A GARDEN"
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.Font = Enum.Font.GothamBold
title.TextSize = 14

-- Dropdown hạt giống (giả lập)
local seedDropdown = Instance.new("TextLabel", frame)
seedDropdown.Position = UDim2.new(0.05, 0, 0.2, 0)
seedDropdown.Size = UDim2.new(0.9, 0, 0, 20)
seedDropdown.Text = "Seeds List: Tomato"
seedDropdown.TextColor3 = Color3.fromRGB(255, 255, 255)
seedDropdown.BackgroundColor3 = Color3.fromRGB(55, 55, 55)
seedDropdown.Font = Enum.Font.Gotham
seedDropdown.TextSize = 12

-- Nút Plant
local plantBtn = Instance.new("TextButton", frame)
plantBtn.Position = UDim2.new(0.05, 0, 0.35, 0)
plantBtn.Size = UDim2.new(0.9, 0, 0, 25)
plantBtn.Text = "Plant"
plantBtn.BackgroundColor3 = Color3.fromRGB(80, 120, 60)
plantBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
plantBtn.Font = Enum.Font.GothamBold
plantBtn.TextSize = 14

-- Checkbox 1: Collect Seeds
local collectBox = Instance.new("TextButton", frame)
collectBox.Position = UDim2.new(0.05, 0, 0.55, 0)
collectBox.Size = UDim2.new(0.4, 0, 0, 25)
collectBox.Text = "✔ Collect Seeds"
collectBox.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
collectBox.TextColor3 = Color3.fromRGB(255, 255, 255)
collectBox.Font = Enum.Font.Gotham
collectBox.TextSize = 12

-- Checkbox 2: Sell All
local sellBox = Instance.new("TextButton", frame)
sellBox.Position = UDim2.new(0.55, 0, 0.55, 0)
sellBox.Size = UDim2.new(0.4, 0, 0, 25)
sellBox.Text = "✔ Sell All"
sellBox.BackgroundColor3 = Color3.fromRGB(60, 60, 60)
sellBox.TextColor3 = Color3.fromRGB(255, 255, 255)
sellBox.Font = Enum.Font.Gotham
sellBox.TextSize = 12

-- Nút bật/tắt spam E
local toggleBtn = Instance.new("TextButton", frame)
toggleBtn.Position = UDim2.new(0.05, 0, 0.75, 0)
toggleBtn.Size = UDim2.new(0.9, 0, 0, 30)
toggleBtn.Text = "Turn ON"
toggleBtn.BackgroundColor3 = Color3.fromRGB(90, 90, 90)
toggleBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
toggleBtn.Font = Enum.Font.GothamBold
toggleBtn.TextSize = 14

-- Logic bật tắt spam E
local VirtualInputManager = game:GetService("VirtualInputManager")
local isSpamOn = false

toggleBtn.MouseButton1Click:Connect(function()
    isSpamOn = not isSpamOn
    toggleBtn.Text = isSpamOn and "Turn OFF" or "Turn ON"

    if isSpamOn then
        task.spawn(function()
            while isSpamOn do
                task.wait(0.1)
                VirtualInputManager:SendKeyEvent(true, Enum.KeyCode.E, false, game)
                task.wait(0.05)
                VirtualInputManager:SendKeyEvent(false, Enum.KeyCode.E, false, game)
            end
        end)
    end
end)

-- Checkbox toggle logic
local function toggleCheck(btn)
    if string.sub(btn.Text, 1, 1) == "✔" then
        btn.Text = "✘" .. string.sub(btn.Text, 2)
    else
        btn.Text = "✔" .. string.sub(btn.Text, 2)
    end
end

collectBox.MouseButton1Click:Connect(function()
    toggleCheck(collectBox)
end)

sellBox.MouseButton1Click:Connect(function()
    toggleCheck(sellBox)
end)

-- Plant button (chưa gắn logic thật, bạn có thể thêm nếu cần)
plantBtn.MouseButton1Click:Connect(function()
    print("Plant pressed - Bạn có thể thêm code trồng ở đây")
end)
