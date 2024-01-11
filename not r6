local chr = owner.Character

function create(obj, ...)
    local object = Instance.new(obj)
    local par = nil
    
    for i, v in next, (...) do
        if tostring(i) ~= "Parent" then
            object[i] = v
        else
            par = v
        end
    end
    
    if par ~= nil then
        object.Parent = par
    end
    
    return object
end

local fakeR6 = create("Model", {Parent = chr})

for _,v in pairs(chr:GetChildren()) do
	if v:IsA("MeshPart") and v.Name ~= "Head" then
		v.Transparency = 1
	end
end

local fakeTorso = create("Part", {
    Name = "Torso",
    CanCollide = false,
    Massless = false,
    Color = chr:FindFirstChild("UpperTorso").Color,
    Size = Vector3.new(2, 2, 1),
    Parent = fakeR6
})

local fakeRArm = create("Part", {
    Name = "Right Arm",
    CanCollide = false,
    Massless = false,
    Color = chr:FindFirstChild("RightUpperArm").Color,
    Size = Vector3.new(1, 2, 1),
    Parent = fakeR6
})

local fakeLArm = create("Part", {
    Name = "Left Arm",
    CanCollide = false,
    Massless = false,
    Color = chr:FindFirstChild("LeftUpperArm").Color,
    Size = Vector3.new(1, 2, 1),
    Parent = fakeR6
})

local fakeRLeg = create("Part", {
    Name = "Right Leg",
    CanCollide = false,
    Massless = false,
    Color = chr:FindFirstChild("RightUpperLeg").Color,
    Size = Vector3.new(1, 2, 1),
    Parent = fakeR6
})

local fakeLLeg = create("Part", {
    Name = "Left Leg",
    CanCollide = false,
    Massless = false,
    Color = chr:FindFirstChild("LeftUpperLeg").Color,
    Size = Vector3.new(1, 2, 1),
    Parent = fakeR6
})

local torsoWeld = create("Weld", {
    Part0 = fakeTorso,
    Part1 = chr:FindFirstChild("UpperTorso"),
    C0 = CFrame.new(0, 0.25, 0),
    Parent = fakeTorso
})

local rShoulderWeld = create("Weld", {
    Part0 = fakeRArm,
    Part1 = chr:FindFirstChild("RightLowerArm"),
    C0 = CFrame.new(0, -0.1, 0),
    Parent = fakeRArm
})

local lShoulderWeld = create("Weld", {
    Part0 = fakeLArm,
    Part1 = chr:FindFirstChild("LeftLowerArm"),
    C0 = CFrame.new(0, -0.1, 0),
    Parent = fakeLArm
})

local rHipWeld = create("Weld", {
    Part0 = fakeRLeg,
    Part1 = chr:FindFirstChild("RightLowerLeg"),
    C0 = CFrame.new(0, -0.15, 0),
    Parent = fakeRLeg
})

local lHipWeld = create("Weld", {
    Part0 = fakeLLeg,
    Part1 = chr:FindFirstChild("LeftLowerLeg"),
    C0 = CFrame.new(0, -0.15, 0),
    Parent = fakeLLeg
})

local fakeHum = create("Humanoid", {Parent = fakeR6, PlatformStand = true})

local fakeAnim = chr.Animate:Clone()
fakeAnim.Parent = fakeR6

local fakeAnimator = chr.Humanoid.Animator:Clone()
fakeAnimator.Parent = fakeHum

local shirt = chr:FindFirstChildOfClass("Shirt")
local pants = chr:FindFirstChildOfClass("Pants")

if shirt then
	fakeShirt = shirt:Clone()
	fakeShirt.Parent = fakeR6
end

if pants then
	fakePants = pants:Clone()
	fakePants.Parent = fakeR6
end
