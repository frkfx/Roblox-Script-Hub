local duration = 10 -- integer only, no decimals



if game:GetService("SoundService").RespectFilteringEnabled then return end

local sounds = {}

for i,v in pairs(workspace:GetDescendants()) do
    if v:IsA("Sound") and v.Parent.Name ~= "HumanoidRootPart" then
        table.insert(sounds,v)
    end
end


local con = workspace.DescendantAdded:Connect(function(v)
    if v:IsA("Sound") and v.Parent.Name ~= "HumanoidRootPart" then
        table.insert(sounds,v)
    end
end)
wait(.1)
local start = math.floor(tick())
repeat
    for i,v in pairs(sounds) do
        v:Play()
        v.TimePosition = math.random(0,v.TimeLength * 1000)/1000
        task.wait()
    end
until math.floor(tick()) == start + duration
con:Disconnect()

for i,v in pairs(sounds) do
    v:Stop()
end
