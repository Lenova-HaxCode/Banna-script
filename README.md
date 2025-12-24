local hwidplrs = game:GetService("RbxAnalyticsService"):GetClientId()
local keychecked = false

if _G.Key == "DXxrKpQSKZux9oNDv7CqttnLDxr1AcDV" then
    keychecked = true
end

local HWID = {
    "B838DF19-3D2A-42C5-8603-2072EB8F6699",
    "B838DF19-3D2A-42C5-8603-2072EB8F6699111"
}

local allowed = false
for _, id in ipairs(HWID) do
    if hwidplrs == id then
        allowed = true
        break
    end
end

if keychecked and allowed then
    local library = loadstring(game:HttpGet(
    "https://raw.githubusercontent.com/bloodball/-back-ups-for-libs/main/polar"
))()

local ok = library:CreateWindow("hello!")
ok:Section("Main")

------------------------------------------------
-- ตัวแปรหลัก
------------------------------------------------
local Farmc = 0
getgenv()._G.Cowfarm = false

------------------------------------------------
-- ปุ่มวาร์ป
------------------------------------------------
ok:Button("กดตรงนี้ก่อน", function()
    local HRP = game.Players.LocalPlayer.Character.HumanoidRootPart

    HRP.CFrame = CFrame.new(-1397.11841, 16.99, -157.71)
    task.wait(0.1)

    HRP.CFrame = CFrame.new(-451.63, 7.96, 1158.83)
    task.wait(0.1)

    HRP.CFrame = CFrame.new(636.44, 7.60, 178.01)
    task.wait(0.1)

    HRP.CFrame = CFrame.new(-1397.11841, 16.99, -157.71)
    ---------------------------------------------------------------------------
    workspace.Plants.Cow:GetChildren()[8].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow["\224\184\167\224\184\177\224\184\167\224\184\129\224\184\180\224\184\153\224\184\171\224\184\141\224\185\137\224\184\178"].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow:GetChildren()[7].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow:GetChildren()[6].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow:GetChildren()[9].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow:GetChildren()[5].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow["\224\184\167\224\184\177\224\184\167\224\184\162\224\184\183\224\184\153"].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow:GetChildren()[4].Cube.ProximityPrompt.HoldDuration = 0

workspace.Plants.Cow:GetChildren()[3].Cube.ProximityPrompt.HoldDuration = 0
end)

------------------------------------------------
-- ใส่จำนวนเนื้อ
------------------------------------------------
ok:Box("ใส่จำนวนเนื้อ", function(object)
    local num = tonumber(object.Text)
    if num then
        Farmc = num
    end
end)

------------------------------------------------
-- Toggle ฟาร์มวัว
------------------------------------------------
ok:Toggle("ฟาร์มวัว", function(state)
    _G.Cowfarm = state
game.Players.LocalPlayer.Character.HumanoidRootPart.CFrame = CFrame.new(
    -1397.11841, 16.9941483, -157.714432,
    -0.134094402, 0, -0.990968585,
    0, 1, 0,
    0.990968585, 0, -0.134094402
)
    if not state then return end

    task.spawn(function()
        while _G.Cowfarm do
            task.wait()

            local Player = game.Players.LocalPlayer
            local Char = Player.Character
            local HRP = Char.HumanoidRootPart
            local prox = workspace.AutoFarms.Cow.Attachment.ProximityPrompt
    
            fireproximityprompt(prox)

            if Player.Inventory.Meat.Value >= Farmc then
                task.wait(1.5)

                HRP.CFrame = CFrame.new(-1439.79, 16.99, -92.70)

                task.wait(1.5)
                game.ReplicatedStorage.Events.CraftEvent:FireServer(
                    "Craft_Farm",
                    "Meat",
                    Player.Inventory.Meat.Value
                )

            elseif Player.Inventory.Steak.Value >= Farmc then
                HRP.CFrame = CFrame.new(-440.62, 7.31, 1146.26)

                task.wait(1)
                game.ReplicatedStorage.Events.SellEvent:FireServer(
                    "Steak",
                    Player.Inventory.Steak.Value
                )

                task.wait(1.5)
                HRP.CFrame = CFrame.new(-1397.11, 16.99, -157.71)
            end
        end
    end)
end)

else
    game.Players.LocalPlayer:Kick("HWID ไม่ถูกต้อง หรือ Key ผิด")
end
