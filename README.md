_G.PartNeon = s

spawn(function()
    game:GetService("RunService").Heartbeat:Connect(function()
        if _G.PartNeon then
            if not game.Workspace:FindFirstChild("LOL") then
                local PartNeon = Instance.new("Part")
                PartNeon.Name = "LOL"
                PartNeon.Parent = game.Workspace
                PartNeon.Anchored = true
                PartNeon.Transparency = 0
                PartNeon.Size = Vector3.new(30, 0.5, 30)
                PartNeon.Material = "Neon"

                while wait() do
                    local colors = {
                        Color3.fromRGB(255, 0, 0),
                        Color3.fromRGB(255, 155, 0),
                        Color3.fromRGB(255, 255, 0),
                        Color3.fromRGB(0, 255, 0),
                        Color3.fromRGB(0, 255, 255),
                        Color3.fromRGB(0, 155, 255),
                        Color3.fromRGB(255, 0, 255),
                        Color3.fromRGB(255, 0, 155)
                    }

                    for i, color in ipairs(colors) do
                        game:GetService('TweenService'):Create(PartNeon, TweenInfo.new(1, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut), {Color = color}):Play()
                        wait(0.5)
                    end
                end
            else
                game.Workspace["LOL"].CFrame = CFrame.new(game.Players.LocalPlayer.Character.HumanoidRootPart.Position.X, game.Players.LocalPlayer.Character.HumanoidRootPart.Position.Y - 3.92, game.Players.LocalPlayer.Character.HumanoidRootPart.Position.Z)
            end
        else
            if game.Workspace:FindFirstChild("LOL") then
                game.Workspace:FindFirstChild("LOL"):Destroy()
            end
        end
    end)
end)
