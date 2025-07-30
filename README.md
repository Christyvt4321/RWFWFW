local killAuraRange = 10
while true do
    for _, player in pairs(game:GetService("Players"):GetPlayers()) do
        if player ~= game.Players.LocalPlayer and player.Character and player.Character:FindFirstChild("Humanoid") then
            local distance = (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - player.Character.HumanoidRootPart.Position).Magnitude
            if distance <= killAuraRange then
                game:GetService("ReplicatedStorage").DamageRemote:FireServer(player.Character.Humanoid)
            end
        end
    end
    wait()
end
