local a = {flags = {}, windows = {}, open = true}
local b = game:GetService("RunService")
local c = game:GetService("TweenService")
local d = game:GetService("TextService")
local e = game:GetService("UserInputService")
local f = Enum.UserInputType.MouseButton1
local g, h, i, j, k
local function l(z, A)
	A = A or 1
	local B = math.floor(z / A + (math.sign(z) * 0.5)) * A
	if B < 0 then
		B = B + A
	end
	return B
end
local function m(C, D)
	for E, F in next, D do
		if F == C then
			return true
		end
	end
end
local function n(G)
	local H = G.Position - i
	local I = (j.Y.Offset + H.Y) < -36 and -36 or j.Y.Offset + H.Y
	k:TweenPosition(UDim2.new(j.X.Scale, j.X.Offset + H.X, j.Y.Scale, I), "Out", "Quint", 0.1, true)
end
function a:Create(J, K)
	K = typeof(K) == "table" and K or {}
	local L = Instance.new(J)
	for M, N in next, K do
		L[M] = N
	end
	return L
end
local function o(P, Q, R, S)
	local T = S and 28 or 32
	R.main = a:Create("ImageButton", {
		LayoutOrder = S and R.position or 0,
		Position = UDim2.new(0, 20 + (193 * (R.position or 0)), 0, 20),
		Size = UDim2.new(0, 185, 0, T),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(20, 20, 20),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.04,
		ClipsDescendants = true,
		Parent = Q
	})
	if not S then
		U = a:Create("ImageLabel", {
			Size = UDim2.new(1, 0, 0, T),
			BackgroundTransparency = 1,
			Image = "rbxassetid://3570695787",
			ImageColor3 = R.open and (S and Color3.fromRGB(16, 16, 16) or Color3.fromRGB(10, 10, 10)) or (S and Color3.fromRGB(10, 10, 10) or Color3.fromRGB(6, 6, 6)),
			ScaleType = Enum.ScaleType.Slice,
			SliceCenter = Rect.new(100, 100, 100, 100),
			SliceScale = 0.04,
			Parent = R.main
		})
	end
	local V = a:Create("TextLabel", {
		Size = UDim2.new(1, 0, 0, T),
		BackgroundTransparency = S and 0 or 1,
		BackgroundColor3 = Color3.fromRGB(10, 10, 10),
		BorderSizePixel = 0,
		Text = P,
		TextSize = S and 14 or 15,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = S and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(0, 0, 0, 0),
		TextTransparency = S and 0 or 1,
		TextXAlignment = S and Enum.TextXAlignment.Left or Enum.TextXAlignment.Center,
		TextWrapped = false,
		Parent = R.main
	})
	local VOverlay
	if not S then
		VOverlay = a:Create("TextLabel", {
			Size = UDim2.new(0, 185, 0, T),
			BackgroundTransparency = 1,
			BorderSizePixel = 0,
			Text = P,
			TextSize = 15,
			Font = Enum.Font.LuckiestGuy,
			TextColor3 = Color3.fromRGB(255, 255, 255),
			TextTransparency = 0,
			TextXAlignment = Enum.TextXAlignment.Center,
			TextWrapped = false,
			ClipsDescendants = false,
			ZIndex = 10,
			Parent = Q
		})
		game:GetService("RunService").RenderStepped:Connect(function()
			if R.main and R.main.Parent then
				VOverlay.Position = UDim2.new(0, R.main.AbsolutePosition.X, 0, R.main.AbsolutePosition.Y)
				VOverlay.Visible = R.main.Visible
			end
		end)
	end
	if S then
		a:Create("UIPadding", {
			PaddingLeft = UDim.new(0, 8),
			Parent = V
		})
		a:Create("UICorner", {
			CornerRadius = UDim.new(0, 4),
			Parent = V
		})
	end
	local W = a:Create("Frame", {
		Position = UDim2.new(1, 0, 0, 0),
		Size = UDim2.new(-1, 0, 1, 0),
		SizeConstraint = Enum.SizeConstraint.RelativeYY,
		BackgroundTransparency = 1,
		Parent = V
	})
	local X = a:Create("ImageLabel", {
		AnchorPoint = Vector2.new(0.5, 0.5),
		Position = UDim2.new(0.5, 0, 0.5, 0),
		Size = UDim2.new(1, -T - 4, 1, -T - 4),
		Rotation = R.open and 90 or 180,
		BackgroundTransparency = 1,
		Image = "rbxassetid://4918373417",
		ImageColor3 = R.open and Color3.fromRGB(50, 50, 50) or Color3.fromRGB(30, 30, 30),
		ScaleType = Enum.ScaleType.Fit,
		Parent = W
	})
	R.content = a:Create("Frame", {
		Position = UDim2.new(0, 0, 0, T),
		Size = UDim2.new(1, 0, 1, -T),
		BackgroundTransparency = 1,
		Parent = R.main
	})
	local Y = a:Create("UIListLayout", {
		SortOrder = Enum.SortOrder.LayoutOrder,
		Parent = R.content
	})
	Y.Changed:connect(function()
		R.content.Size = UDim2.new(1, 0, 0, Y.AbsoluteContentSize.Y)
		R.main.Size = #R.options > 0 and R.open and UDim2.new(0, 185, 0, Y.AbsoluteContentSize.Y + T) or UDim2.new(0, 185, 0, T)
	end)
	if not S then
		a:Create("UIPadding", {
			Parent = R.content
		})
		V.InputBegan:connect(function(Z)
			if Z.UserInputType == f then
				k = R.main
				g = true
				i = Z.Position
				j = k.Position
			elseif Z.UserInputType == Enum.UserInputType.Touch then
				k = R.main
				g = true
				i = Z.Position
				j = k.Position
			end
		end)
		V.InputChanged:connect(function(aa)
			if g and aa.UserInputType == Enum.UserInputType.MouseMovement then
				h = aa
			elseif g and aa.UserInputType == Enum.UserInputType.Touch then
				h = aa
			end
		end)
		V.InputEnded:connect(function(ab)
			if ab.UserInputType == f then
				g = false
			elseif ab.UserInputType == Enum.UserInputType.Touch then
				g = false
			end
		end)
	end
	W.InputBegan:connect(function(ac)
		if ac.UserInputType == f then
			R.open = not R.open
			c:Create(X, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {Rotation = R.open and 90 or 180, ImageColor3 = R.open and Color3.fromRGB(50, 50, 50) or Color3.fromRGB(30, 30, 30)}):Play()
			if S then
				c:Create(V, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = R.open and Color3.fromRGB(16, 16, 16) or Color3.fromRGB(10, 10, 10)}):Play()
			else
				c:Create(U, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = R.open and Color3.fromRGB(10, 10, 10) or Color3.fromRGB(6, 6, 6)}):Play()
			end
			R.main:TweenSize(#R.options > 0 and R.open and UDim2.new(0, 185, 0, Y.AbsoluteContentSize.Y + T) or UDim2.new(0, 185, 0, T), "Out", "Quad", 0.2, true)
		elseif ac.UserInputType == Enum.UserInputType.Touch then
			R.open = not R.open
			c:Create(X, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {Rotation = R.open and 90 or 180, ImageColor3 = R.open and Color3.fromRGB(50, 50, 50) or Color3.fromRGB(30, 30, 30)}):Play()
			if S then
				c:Create(V, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = R.open and Color3.fromRGB(16, 16, 16) or Color3.fromRGB(10, 10, 10)}):Play()
			else
				c:Create(U, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = R.open and Color3.fromRGB(10, 10, 10) or Color3.fromRGB(6, 6, 6)}):Play()
			end
			R.main:TweenSize(#R.options > 0 and R.open and UDim2.new(0, 185, 0, Y.AbsoluteContentSize.Y + T) or UDim2.new(0, 185, 0, T), "Out", "Quad", 0.2, true)
		end
	end)
	function R:SetTitle(ad)
		V.Text = tostring(ad)
		if VOverlay then VOverlay.Text = tostring(ad) end
	end
	return R
end
local function p(ae, af)
	local ag = a:Create("TextLabel", {
		LayoutOrder = ae.position,
		Size = UDim2.new(1, 0, 0, 22),
		BackgroundTransparency = 1,
		Text = "    " .. ae.text,
		TextSize = 13,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextXAlignment = Enum.TextXAlignment.Left,
		Parent = af.content
	})
	setmetatable(ae, {__newindex = function(ah, ai, aj)
		if ai == "Text" then
			ag.Text = "    " .. tostring(aj)
		end
	end})
end
local function q(ak, al)
	local am = a:Create("TextLabel", {
		LayoutOrder = ak.position,
		Size = UDim2.new(1, 0, 0, 26),
		BackgroundTransparency = 1,
		Text = "    " .. ak.text,
		TextSize = 13,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextXAlignment = Enum.TextXAlignment.Left,
		Parent = al.content
	})
	local an = a:Create("ImageLabel", {
		Position = UDim2.new(1, -22, 0.5, -8),
		Size = UDim2.new(0, 16, 0, 16),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = ak.state and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(100, 100, 100),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = am
	})
	local ao = a:Create("ImageLabel", {
		Position = UDim2.new(0, 2, 0, 2),
		Size = UDim2.new(1, -4, 1, -4),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = ak.state and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(20, 20, 20),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = an
	})
	local ap = a:Create("Frame", {
		Position = UDim2.new(0, 3, 0, 3),
		Size = ak.state and UDim2.new(1, -6, 1, -6) or UDim2.new(0, 0, 1, -6),
		BackgroundTransparency = 1,
		ClipsDescendants = true,
		Parent = an
	})
	local aq = a:Create("ImageLabel", {
		Size = UDim2.new(1, 0, 1, 0),
		BackgroundTransparency = 1,
		Image = "rbxassetid://4919148038",
		ImageColor3 = Color3.fromRGB(20, 20, 20),
		Parent = ap
	})
	local ar
	am.InputBegan:connect(function(as)
		if as.UserInputType == f then
			ak:SetState(not ak.state)
		elseif as.UserInputType == Enum.UserInputType.Touch then
			ak:SetState(not ak.state)
		end
		if as.UserInputType == Enum.UserInputType.MouseMovement then
			ar = true
			if not ak.state then
				c:Create(an, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(140, 140, 140)}):Play()
			end
		end
	end)
	am.InputEnded:connect(function(at)
		if at.UserInputType == Enum.UserInputType.MouseMovement then
			ar = true
			if not ak.state then
				c:Create(an, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(100, 100, 100)}):Play()
			end
		end
	end)
	function ak:SetState(au)
		a.flags[self.flag] = au
		self.state = au
		ap:TweenSize(ak.state and UDim2.new(1, -6, 1, -6) or UDim2.new(0, 0, 1, -6), "Out", "Quad", 0.2, true)
		c:Create(ao, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = au and Color3.fromRGB(255, 255, 255) or Color3.fromRGB(20, 20, 20)}):Play()
		if au then
			c:Create(an, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
		else
			if ar then
				c:Create(an, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(140, 140, 140)}):Play()
			else
				c:Create(an, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(100, 100, 100)}):Play()
			end
		end
		self.callback(au)
	end
	if ak.state then
		delay(1, function() ak.callback(true) end)
	end
	setmetatable(ak, {__newindex = function(ah, ai, aj)
		if ai == "Text" then
			am.Text = "    " .. tostring(aj)
		end
	end})
end
local function r(av, aw)
	local ax = a:Create("TextLabel", {
		ZIndex = 2,
		LayoutOrder = av.position,
		Size = UDim2.new(1, 0, 0, 28),
		BackgroundTransparency = 1,
		Text = " " .. av.text,
		TextSize = 13,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(255, 255, 255),
		Parent = aw.content
	})
	local ay = a:Create("ImageLabel", {
		AnchorPoint = Vector2.new(0.5, 0.5),
		Position = UDim2.new(0.5, 0, 0.5, 0),
		Size = UDim2.new(1, -12, 1, -6),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(40, 40, 40),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = ax
	})
	local az
	local ba
	ax.InputBegan:connect(function(bb)
		if bb.UserInputType == f then
			a.flags[av.flag] = true
			ba = true
			c:Create(ay, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(80, 80, 80)}):Play()
			av.callback()
		elseif bb.UserInputType == Enum.UserInputType.Touch then
			a.flags[av.flag] = true
			ba = true
			c:Create(ay, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(80, 80, 80)}):Play()
			av.callback()
		end
		if bb.UserInputType == Enum.UserInputType.MouseMovement then
			az = true
			c:Create(ay, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(60, 60, 60)}):Play()
		end
	end)
	ax.InputEnded:connect(function(bc)
		if bc.UserInputType == f then
			ba = false
			if az then
				c:Create(ay, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(60, 60, 60)}):Play()
			else
				c:Create(ay, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(40, 40, 40)}):Play()
			end
		elseif bc.UserInputType == Enum.UserInputType.Touch then
			ba = false
			if az then
				c:Create(ay, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(60, 60, 60)}):Play()
			else
				c:Create(ay, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(40, 40, 40)}):Play()
			end
		end
		if bc.UserInputType == Enum.UserInputType.MouseMovement then
			az = false
			if not ba then
				c:Create(ay, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(40, 40, 40)}):Play()
			end
		end
	end)
end
local function s(bd, be, bf)
	local bg = 0
	local bh = a:Create("Frame", {
		LayoutOrder = bd.position,
		Size = UDim2.new(1, 0, 0, 44),
		BackgroundTransparency = 1,
		Parent = be.content
	})
	local bi = a:Create("ImageLabel", {
		Position = UDim2.new(0, 6, 0, 4),
		Size = UDim2.new(1, -12, 1, -8),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(40, 40, 40),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = bh
	})
	local bj = a:Create("TextLabel", {
		Position = UDim2.new(0, 10, 0, 6),
		Size = UDim2.new(1, -20, 0, 12),
		BackgroundTransparency = 1,
		Text = bd.text,
		TextSize = 12,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(140, 140, 140),
		TextXAlignment = Enum.TextXAlignment.Left,
		Parent = bh
	})
	local bk = a:Create("TextLabel", {
		Position = UDim2.new(0, 10, 0, 18),
		Size = UDim2.new(1, -20, 0, 20),
		BackgroundTransparency = 1,
		Text = bd.value,
		TextSize = 13,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextXAlignment = Enum.TextXAlignment.Left,
		Parent = bh
	})
	a:Create("ImageLabel", {
		Position = UDim2.new(1, -14, 0, 12),
		Size = UDim2.new(-1, 24, 1, -24),
		SizeConstraint = Enum.SizeConstraint.RelativeYY,
		Rotation = 90,
		BackgroundTransparency = 1,
		Image = "rbxassetid://4918373417",
		ImageColor3 = Color3.fromRGB(140, 140, 140),
		ScaleType = Enum.ScaleType.Fit,
		Parent = bi
	})
	bd.mainHolder = a:Create("ImageButton", {
		ZIndex = 3,
		Size = UDim2.new(0, 185, 0, 44),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageTransparency = 1,
		ImageColor3 = Color3.fromRGB(30, 30, 30),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Visible = false,
		Parent = a.base
	})
	local bl = a:Create("ScrollingFrame", {
		ZIndex = 3,
		Size = UDim2.new(1, 0, 1, 0),
		BackgroundTransparency = 1,
		BorderSizePixel = 0,
		ScrollBarImageColor3 = Color3.fromRGB(),
		ScrollBarThickness = 0,
		ScrollingDirection = Enum.ScrollingDirection.Y,
		Parent = bd.mainHolder
	})
	a:Create("UIPadding", {
		PaddingTop = UDim.new(0, 6),
		Parent = bl
	})
	local bm = a:Create("UIListLayout", {
		Parent = bl
	})
	bm.Changed:connect(function()
		bd.mainHolder.Size = UDim2.new(0, 185, 0, (bg > 4 and (4 * 30) or bm.AbsoluteContentSize.Y) + 12)
		bl.CanvasSize = UDim2.new(0, 0, 0, bm.AbsoluteContentSize.Y + 12)
	end)
	local bn
	bi.InputBegan:connect(function(bu)
		if bu.UserInputType == f then
			if a.activePopup then
				a.activePopup:Close()
			end
			local dn = bh.AbsolutePosition
			bd.mainHolder.Position = UDim2.new(0, dn.X - 5, 0, dn.Y - 10)
			bd.open = true
			bd.mainHolder.Visible = true
			a.activePopup = bd
			bl.ScrollBarThickness = 4
			c:Create(bd.mainHolder, TweenInfo.new(0.3, Enum.EasingStyle.Quint, Enum.EasingDirection.Out), {ImageTransparency = 0, Position = UDim2.new(0, dn.X - 5, 0, dn.Y - 4)}):Play()
			c:Create(bd.mainHolder, TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.1), {Position = UDim2.new(0, dn.X - 5, 0, dn.Y + 1)}):Play()
			for dp, dq in next, bl:GetChildren() do
				if dq:IsA"TextLabel" then
					c:Create(dq, TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundTransparency = 0, TextTransparency = 0}):Play()
				end
			end
		elseif bu.UserInputType == Enum.UserInputType.Touch then
			if a.activePopup then
				a.activePopup:Close()
			end
			local dn = bh.AbsolutePosition
			bd.mainHolder.Position = UDim2.new(0, dn.X - 5, 0, dn.Y - 10)
			bd.open = true
			bd.mainHolder.Visible = true
			a.activePopup = bd
			bl.ScrollBarThickness = 4
			c:Create(bd.mainHolder, TweenInfo.new(0.3, Enum.EasingStyle.Quint, Enum.EasingDirection.Out), {ImageTransparency = 0, Position = UDim2.new(0, dn.X - 5, 0, dn.Y - 4)}):Play()
			c:Create(bd.mainHolder, TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out, 0, false, 0.1), {Position = UDim2.new(0, dn.X - 5, 0, dn.Y + 1)}):Play()
			for dp, dq in next, bl:GetChildren() do
				if dq:IsA"TextLabel" then
					c:Create(dq, TweenInfo.new(0.4, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundTransparency = 0, TextTransparency = 0}):Play()
				end
			end
		end
		if bu.UserInputType == Enum.UserInputType.MouseMovement then
			bn = true
			if not bd.open then
				c:Create(bi, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(60, 60, 60)}):Play()
			end
		end
	end)
	bi.InputEnded:connect(function(bv)
		if bv.UserInputType == Enum.UserInputType.MouseMovement then
			bn = false
			if not bd.open then
				c:Create(bi, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(40, 40, 40)}):Play()
			end
		end
	end)
	function bd:AddValue(bo)
		bg = bg + 1
		local bp = a:Create("TextLabel", {
			ZIndex = 3,
			Size = UDim2.new(1, 0, 0, 30),
			BackgroundColor3 = Color3.fromRGB(30, 30, 30),
			BorderSizePixel = 0,
			Text = "    " .. bo,
			TextSize = 12,
			TextTransparency = self.open and 0 or 1,
			Font = Enum.Font.LuckiestGuy,
			TextColor3 = Color3.fromRGB(255, 255, 255),
			TextXAlignment = Enum.TextXAlignment.Left,
			Parent = bl
		})
		local bq
		local br
		bp.InputBegan:connect(function(bs)
			if bs.UserInputType == f then
				br = true
				c:Create(bp, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(10, 10, 10)}):Play()
				self:SetValue(bo)
			elseif bs.UserInputType == Enum.UserInputType.Touch then
				br = true
				c:Create(bp, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(10, 10, 10)}):Play()
				self:SetValue(bo)
			end
			if bs.UserInputType == Enum.UserInputType.MouseMovement then
				bq = true
				if not br then
					c:Create(bp, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(20, 20, 20)}):Play()
				end
			end
		end)
		bp.InputEnded:connect(function(bt)
			if bt.UserInputType == f then
				br = false
				c:Create(bp, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = bq and Color3.fromRGB(20, 20, 20) or Color3.fromRGB(30, 30, 30)}):Play()
			elseif bt.UserInputType == Enum.UserInputType.Touch then
				br = false
				c:Create(bp, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = bq and Color3.fromRGB(20, 20, 20) or Color3.fromRGB(30, 30, 30)}):Play()
			end
			if bt.UserInputType == Enum.UserInputType.MouseMovement then
				bq = false
				if not br then
					c:Create(bp, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundColor3 = Color3.fromRGB(30, 30, 30)}):Play()
				end
			end
		end)
	end
	if not table.find(bd.values, bd.value) then
		bd:AddValue(bd.value)
	end
	for _, bo in next, bd.values do
		bd:AddValue(tostring(bo))
	end
	function bd:RemoveValue(bo)
		for dp, dq in next, bl:GetChildren() do
			if dq:IsA"TextLabel" and dq.Text == "	" .. bo then
				dq:Destroy()
				bg = bg - 1
				break
			end
		end
		if self.value == bo then
			self:SetValue("")
		end
	end
	function bd:SetValue(bw)
		a.flags[self.flag] = tostring(bw)
		self.value = tostring(bw)
		bk.Text = self.value
		self.callback(bw)
	end
	function bd:Close()
		a.activePopup = nil
		self.open = false
		bl.ScrollBarThickness = 0
		local dn = bh.AbsolutePosition
		c:Create(bi, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = bn and Color3.fromRGB(60, 60, 60) or Color3.fromRGB(40, 40, 40)}):Play()
		c:Create(self.mainHolder, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageTransparency = 1, Position = UDim2.new(0, dn.X - 5, 0, dn.Y - 10)}):Play()
		for dp, dq in next, bl:GetChildren() do
			if dq:IsA"TextLabel" then
				c:Create(dq, TweenInfo.new(0.3, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {BackgroundTransparency = 1, TextTransparency = 1}):Play()
			end
		end
		wait(0.3)
		if not self.open then
			self.mainHolder.Visible = false
		end
	end
	return bd
end
local function t(bx, by)
	local bz = a:Create("Frame", {
		LayoutOrder = bx.position,
		Size = UDim2.new(1, 0, 0, 48),
		BackgroundTransparency = 1,
		Parent = by.content
	})
	local ca = a:Create("ImageLabel", {
		Position = UDim2.new(0, 6, 0, 4),
		Size = UDim2.new(1, -12, 1, -8),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(60, 60, 60),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = bz
	})
	local cb = a:Create("ImageLabel", {
		Position = UDim2.new(0, 8, 0, 6),
		Size = UDim2.new(1, -16, 1, -12),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(20, 20, 20),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.01,
		Parent = bz
	})
	local cc = a:Create("TextLabel", {
		Position = UDim2.new(0, 12, 0, 10),
		Size = UDim2.new(1, -24, 0, 14),
		BackgroundTransparency = 1,
		Text = bx.text,
		TextSize = 12,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(100, 100, 100),
		TextXAlignment = Enum.TextXAlignment.Left,
		Parent = bz
	})
	local cd = a:Create("TextBox", {
		Position = UDim2.new(0, 12, 0, 22),
		Size = UDim2.new(1, -24, 0, 20),
		BackgroundTransparency = 1,
		Text = bx.value,
		TextSize = 13,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextXAlignment = Enum.TextXAlignment.Left,
		TextWrapped = true,
		Parent = bz
	})
	local ce
	local cf
	bz.InputBegan:connect(function(cg)
		if cg.UserInputType == f then
			if not cf then cd:CaptureFocus() end
		elseif cg.UserInputType == Enum.UserInputType.Touch then
			if not cf then cd:CaptureFocus() end
		end
		if cg.UserInputType == Enum.UserInputType.MouseMovement then
			ce = true
			if not cf then
				c:Create(ca, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(100, 100, 100)}):Play()
			end
		end
	end)
	bz.InputEnded:connect(function(ch)
		if ch.UserInputType == Enum.UserInputType.MouseMovement then
			ce = false
			if not cf then
				c:Create(ca, TweenInfo.new(0.1, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(60, 60, 60)}):Play()
			end
		end
	end)
	cd.Focused:connect(function()
		cf = true
		c:Create(ca, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(255, 255, 255)}):Play()
	end)
	cd.FocusLost:connect(function(ci)
		cf = false
		c:Create(ca, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.Out), {ImageColor3 = Color3.fromRGB(60, 60, 60)}):Play()
		bx:SetValue(cd.Text, ci)
	end)
	function bx:SetValue(cj, ck)
		a.flags[self.flag] = tostring(cj)
		self.value = tostring(cj)
		cd.Text = self.value
		self.callback(cj, ck)
	end
end
local function u(cl, cm)
	local cn = a:Create("Frame", {
		LayoutOrder = cl.position,
		Size = UDim2.new(1, 0, 0, 36),
		BackgroundTransparency = 1,
		Parent = cm.content
	})
	local co = a:Create("TextLabel", {
		Position = UDim2.new(0, 0, 0, 4),
		Size = UDim2.new(1, 0, 0, 16),
		BackgroundTransparency = 1,
		Text = "    " .. cl.text,
		TextSize = 13,
		Font = Enum.Font.LuckiestGuy,
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextXAlignment = Enum.TextXAlignment.Left,
		Parent = cn
	})
	local cp = a:Create("ImageLabel", {
		Position = UDim2.new(0, 10, 0, 26),
		Size = UDim2.new(1, -20, 0, 5),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(40, 40, 40),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = cn
	})
	local cq = a:Create("ImageLabel", {
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(255, 255, 255),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = cp
	})
	local cr = a:Create("ImageLabel", {
		AnchorPoint = Vector2.new(0.5, 0.5),
		Position = UDim2.new((cl.value - cl.min) / (cl.max - cl.min), 0, 0.5, 0),
		SizeConstraint = Enum.SizeConstraint.RelativeYY,
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(255, 255, 255),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 1,
		Parent = cp
	})
	local cs = a:Create("ImageLabel", {
		Position = UDim2.new(1, -6, 0, 4),
		Size = UDim2.new(0, -60, 0, 16),
		BackgroundTransparency = 1,
		Image = "rbxassetid://3570695787",
		ImageColor3 = Color3.fromRGB(40, 40, 40),
		ScaleType = Enum.ScaleType.Slice,
		SliceCenter = Rect.new(100, 100, 100, 100),
		SliceScale = 0.02,
		Parent = cn
	})
	local ct = a:Create("TextBox", {
		Size = UDim2.new(1, 0, 1, 0),
		BackgroundTransparency = 1,
		Text = cl.value,
		TextColor3 = Color3.fromRGB(255, 255, 255),
		TextSize = 13,
		TextWrapped = true,
		Font = Enum.Font.LuckiestGuy,
		Parent = cs
	})
	if cl.min >= 0 then
		cq.Size = UDim2.new((cl.value - cl.min) / (cl.max - cl.min), 0, 1, 0)
	else
		cq.Position = UDim2.new((0 - cl.min) / (cl.max - cl.min), 0, 0, 0)
		cq.Size = UDim2.new(cl.value / (cl.max - cl.min), 0, 1, 0)
	end
	local cu = false
	local function cv(cw)
		cl:SetValue(cl.min + ((cw - cp.AbsolutePosition.X) / cp.AbsoluteSize.X) * (cl.max - cl.min))
	end
	cn.InputBegan:connect(function(cx)
		if cx.UserInputType == f or cx.UserInputType == Enum.UserInputType.Touch then
			cu = true
			cr:TweenSize(UDim2.new(3.5, 0, 3.5, 0), "Out", "Quad", 0.15, true)
			cv(cx.Position.X)
		end
	end)
	e.InputChanged:connect(function(cy)
		if cu then
			if cy.UserInputType == Enum.UserInputType.MouseMovement then
				cv(cy.Position.X)
			elseif cy.UserInputType == Enum.UserInputType.Touch then
				cv(cy.Position.X)
			end
		end
	end)
	cn.InputEnded:connect(function(cz)
		if cz.UserInputType == f or cz.UserInputType == Enum.UserInputType.Touch then
			cu = false
			cr:TweenSize(UDim2.new(2, 0, 2, 0), "Out", "Quad", 0.15, true)
		end
	end)
	ct.FocusLost:connect(function()
		cl:SetValue(tonumber(ct.Text) or cl.value)
	end)
	function cl:SetValue(da)
		da = l(da, cl.float)
		da = math.clamp(da, self.min, self.max)
		cr:TweenPosition(UDim2.new((da - self.min) / (self.max - self.min), 0, 0.5, 0), "Out", "Quad", 0.1, true)
		if self.min >= 0 then
			cq:TweenSize(UDim2.new((da - self.min) / (self.max - self.min), 0, 1, 0), "Out", "Quad", 0.1, true)
		else
			cq:TweenPosition(UDim2.new((0 - self.min) / (self.max - self.min), 0, 0, 0), "Out", "Quad", 0.1, true)
			cq:TweenSize(UDim2.new(da / (self.max - self.min), 0, 1, 0), "Out", "Quad", 0.1, true)
		end
		a.flags[self.flag] = da
		self.value = da
		ct.Text = da
		self.callback(da)
	end
end
local function v(db, dc)
	for dd, de in next, db.options do
		if de.type == "label" then
			p(de, db)
		elseif de.type == "toggle" then
			q(de, db)
		elseif de.type == "button" then
			r(de, db)
		elseif de.type == "list" then
			s(de, db, dc)
		elseif de.type == "box" then
			t(de, db)
		elseif de.type == "slider" then
			u(de, db)
		elseif de.type == "folder" then
			de:init()
		end
	end
end
local function w(de)
	function de:AddLabel(df)
		df = typeof(df) == "table" and df or {}
		df.text = tostring(df.text)
		df.type = "label"
		df.position = #self.options
		table.insert(self.options, df)
		return df
	end
	function de:AddToggle(df)
		df = typeof(df) == "table" and df or {}
		df.text = tostring(df.text)
		df.state = typeof(df.state) == "boolean" and df.state or false
		df.callback = typeof(df.callback) == "function" and df.callback or function() end
		df.type = "toggle"
		df.position = #self.options
		df.flag = df.flag or df.text
		a.flags[df.flag] = df.state
		table.insert(self.options, df)
		return df
	end
	function de:AddButton(df)
		df = typeof(df) == "table" and df or {}
		df.text = tostring(df.text)
		df.callback = typeof(df.callback) == "function" and df.callback or function() end
		df.type = "button"
		df.position = #self.options
		df.flag = df.flag or df.text
		table.insert(self.options, df)
		return df
	end
	function de:AddList(df)
		df = typeof(df) == "table" and df or {}
		df.text = tostring(df.text)
		df.values = typeof(df.values) == "table" and df.values or {}
		df.value = tostring(df.value or df.values[1] or "")
		df.callback = typeof(df.callback) == "function" and df.callback or function() end
		df.open = false
		df.type = "list"
		df.position = #self.options
		df.flag = df.flag or df.text
		a.flags[df.flag] = df.value
		table.insert(self.options, df)
		return df
	end
	function de:AddBox(df)
		df = typeof(df) == "table" and df or {}
		df.text = tostring(df.text)
		df.value = tostring(df.value or "")
		df.callback = typeof(df.callback) == "function" and df.callback or function() end
		df.type = "box"
		df.position = #self.options
		df.flag = df.flag or df.text
		a.flags[df.flag] = df.value
		table.insert(self.options, df)
		return df
	end
	function de:AddSlider(df)
		df = typeof(df) == "table" and df or {}
		df.text = tostring(df.text)
		df.min = typeof(df.min) == "number" and df.min or 0
		df.max = typeof(df.max) == "number" and df.max or 100
		df.float = typeof(df.float) == "number" and df.float or 1
		df.value = typeof(df.value) == "number" and math.clamp(df.value, df.min, df.max) or df.min
		df.callback = typeof(df.callback) == "function" and df.callback or function() end
		df.type = "slider"
		df.position = #self.options
		df.flag = df.flag or df.text
		a.flags[df.flag] = df.value
		table.insert(self.options, df)
		return df
	end
	function de:AddFolder(dg)
		local dh = {}
		dh.title = tostring(dg)
		dh.options = {}
		dh.open = false
		dh.type = "folder"
		dh.position = #self.options
		table.insert(self.options, dh)
		w(dh)
		function dh:init()
			o(self.title, de.content, self, true)
			v(self, de)
		end
		return dh
	end
end
function a:CreateWindow(di)
	if #a.windows >= 3 then return end
	local dj = {title = tostring(di), options = {}, open = true, canInit = true, init = false, position = #a.windows}
	w(dj)
	table.insert(a.windows, dj)
	return dj
end
local x
function a:Init()
	local dk = game:GetService("CoreGui"):FindFirstChild("ToraScript")
	if dk then dk:Destroy() end
	a.base = a:Create("ScreenGui")
	if syn and syn.protect_gui then
		syn.protect_gui(a.base)
	elseif get_hidden_gui then
		get_hidden_gui(a.base)
	elseif gethui then
		gethui(a.base)
	else
		game:GetService("Players").LocalPlayer:Kick("Error: protect_gui function not found")
		return
	end
	a.base.Parent = game:GetService("CoreGui")
	a.base.ResetOnSpawn = true
	a.base.Name = "ToraScript"
	for dl, dj in next, a.windows do
		if dj.canInit and not dj.init then
			dj.init = true
			o(dj.title, a.base, dj)
			v(dj)
		end
	end
	return a.base
end
function a:Close()
	if typeof(a.base) ~= "Instance" then end
	a.open = not a.open
	if a.activePopup then
		a.activePopup:Close()
	end
	for dm, dj in next, a.windows do
		if dj.main then
			dj.main.Visible = a.open
		end
	end
end
e.InputBegan:connect(function(dn)
	if dn.UserInputType == f then
		if a.activePopup then
			if dn.Position.X < a.activePopup.mainHolder.AbsolutePosition.X or dn.Position.Y < a.activePopup.mainHolder.AbsolutePosition.Y then
				a.activePopup:Close()
			end
		end
		if a.activePopup then
			if dn.Position.X > a.activePopup.mainHolder.AbsolutePosition.X + a.activePopup.mainHolder.AbsoluteSize.X or dn.Position.Y > a.activePopup.mainHolder.AbsolutePosition.Y + a.activePopup.mainHolder.AbsoluteSize.Y then
				a.activePopup:Close()
			end
		end
	elseif dn.UserInputType == Enum.UserInputType.Touch then
		if a.activePopup then
			if dn.Position.X < a.activePopup.mainHolder.AbsolutePosition.X or dn.Position.Y < a.activePopup.mainHolder.AbsolutePosition.Y then
				a.activePopup:Close()
			end
		end
		if a.activePopup then
			if dn.Position.X > a.activePopup.mainHolder.AbsolutePosition.X + a.activePopup.mainHolder.AbsoluteSize.X or dn.Position.Y > a.activePopup.mainHolder.AbsolutePosition.Y + a.activePopup.mainHolder.AbsoluteSize.Y then
				a.activePopup:Close()
			end
		end
	end
end)
e.InputChanged:connect(function(dp)
	if dp == h and g then
		n(dp)
	end
end)
wait(1)
local y = game:service("VirtualUser")
game:service("Players").LocalPlayer.Idled:connect(function()
	y:CaptureController()
	y:ClickButton2(Vector2.new())
end)
return a