function checkskillMelee()
	if not game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills:FindFirstChild(NameMelee()) then
		EquipWeapon(NameMelee())
		return false
	end;
	for L_89_forvar0, L_90_forvar1 in next, game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills[NameMelee()]:GetChildren() do
		if L_90_forvar1:IsA("Frame") then
			if L_90_forvar1.Name ~= 'Template' and L_90_forvar1.Title.TextColor3 == Color3.new(1, 1, 1) and L_90_forvar1.Cooldown.Size == UDim2.new(0, 0, 1, - 1) or L_90_forvar1.Cooldown.Size == UDim2.new(1, 0, 1, - 1) then
				return L_90_forvar1.Name
			end
		end
	end
end;
function checkskillDF()
	if not game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills:FindFirstChild(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value) then
		EquipWeapon(game:GetService("Players").LocalPlayer.Data.DevilFruit.Value)
		return false
	end;
	for L_91_forvar0, L_92_forvar1 in next, game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills[game:GetService("Players").LocalPlayer.Data.DevilFruit.Value]:GetChildren() do
		if L_92_forvar1:IsA("Frame") then
			if L_92_forvar1.Name ~= 'Template' and L_92_forvar1.Title.TextColor3 == Color3.new(1, 1, 1) and L_92_forvar1.Cooldown.Size == UDim2.new(0, 0, 1, - 1) or L_92_forvar1.Cooldown.Size == UDim2.new(1, 0, 1, - 1) then
				return L_92_forvar1.Name
			end
		end
	end
end;
function checkskillSword()
	if not NameSword() then
		return
	end;
	if not game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills:FindFirstChild(NameSword()) then
		EquipWeapon(NameSword())
		return false
	end;
	for L_93_forvar0, L_94_forvar1 in next, game:GetService("Players").LocalPlayer.PlayerGui.Main.Skills[NameSword()]:GetChildren() do
		if L_94_forvar1:IsA("Frame") then
			if L_94_forvar1.Name ~= 'Template' and L_94_forvar1.Title.TextColor3 == Color3.new(1, 1, 1) and L_94_forvar1.Cooldown.Size == UDim2.new(0, 0, 1, - 1) or L_94_forvar1.Cooldown.Size == UDim2.new(1, 0, 1, - 1) then
				return L_94_forvar1.Name
			end
		end
	end
end;
