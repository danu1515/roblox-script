local centerPosition = CFrame.new(0, 5, 0)

local player = game.Players.LocalPlayer
local function getHRP()
    local char = player.Character or player.CharacterAdded:Wait()
    return char:WaitForChild("HumanoidRootPart")
end

local stealRemote = nil
for _, v in pairs(game:GetDescendants()) do
    if v:IsA("RemoteEvent") and string.lower(v.Name):find("steal") then
        stealRemote = v
        break
    end
end

if not stealRemote then
    warn("RemoteEvent 'steal' tidak ditemukan.")
    return
end

while true do
    task.wait(1.5)
    pcall(function()
        stealRemote:FireServer()
        task.wait(0.5)
        getHRP().CFrame = centerPosition
    end)
end
