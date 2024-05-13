

local Fluent = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/main.lua"))()
local SaveManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/SaveManager.lua"))()
local InterfaceManager = loadstring(game:HttpGet("https://raw.githubusercontent.com/barlossxi/barlossxi/main/InterfaceManager.lua.txt"))()

local Window = Fluent:CreateWindow({
    Title = "ZA HUB King Legacy VIP Script",
    SubTitle = "",
    TabWidth = 160,
    Size = UDim2.fromOffset(580, 460),
    Acrylic = true, -- The blur may be detectable, setting this to false disables blur entirely
    Theme = "Dark",
    MinimizeKey = Enum.KeyCode.LeftControl -- Used when theres no MinimizeKeybind
})


--Fluent provides Lucide Icons https://lucide.dev/icons/ for the tabs, icons are optional
local Tabs = {
    Main = Window:AddTab({ Title = "Main", Icon = "home" }),
    Event = Window:AddTab({
		Title = "Event", Icon = "backpack"
	}),
    Shop = Window:AddTab({ Title = "SHOP", Icon = "shopping-cart" }),
    Dungeon = Window:AddTab({ Title = "Dungeon", Icon = "swords" }),
    Settings = Window:AddTab({ Title = "Configs", Icon = "settings" })
}

local Options = Fluent.Options

do


Tabs.Main:AddParagraph({

	Title = "Main",

	Content = ""
})

local Grab = Tabs.Main:AddToggle("Grab", {Title = "Auto Farm", Default = false })
    Grab:OnChanged(function(aaabbb)
_G.Boss = aaabbb
_G.Auto_Farm = aaabbb
    end)
    
    
 
    
    
    
    Tabs.Main:AddDropdown("Select Method", {
        Title = "Select Method",
        Values = {"ไม่เลือก","Behind","Below","Upper"},
        Multi = false,
        Default = 1,
        Callback = function(v)
          _G.Method = v
        end
    })
    
    
    
    spawn(function()
        while wait() do 
            pcall(function()
                if _G.Method == "Behind" then
                    MethodFarm = CFrame.new(0,0,_G.DistanceMob)
                elseif _G.Method == "Below" then
                    MethodFarm = CFrame.new(0,-_G.DistanceMob,0) * CFrame.Angles(math.rad(90),0,0)
                elseif _G.Method == "Upper" then
                    MethodFarm = CFrame.new(0,_G.DistanceMob,0)  * CFrame.Angles(math.rad(-90),0,0)
                elseif _G.Method == "ไม่เลือก" then
                    MethodFarm = CFrame.new(0,0,_G.DistanceMob)                
                else
                    MethodFarm = CFrame.new(0,0,_G.DistanceMob)
                end
            end)
        end
    end)


Tabs.Main:AddInput("Input", {
        Title = "Distance Mob",
        Default = "0",
        Placeholder = "ใส่ระยะ",
        Numeric = true, -- Only allows numbers
        Finished = false, -- Only calls callback when you press enter
        Callback = function(gay)
         _G.DistanceMob = gay
        end
    })




--- CONFIG
local Weaponlist = {}

local SelectWeapon = Tabs.Main:AddDropdown("SelectWeapon", {
    Title = "Select Weapon",
    Values = Weaponlist,
    Multi = false,
    Default = false,
    Callback = function(selectedWeapon)
        _G.SelectWeapon = selectedWeapon
        print("Selected " .. _G.SelectWeapon)
    end
})

local function RefreshWeaponList()
    Weaponlist = {}
    for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetChildren()) do
        table.insert(Weaponlist, v.Name)
    end
    SelectWeapon:SetValues(Weaponlist)
end

Tabs.Main:AddButton({
    Title = "Refresh Weapon",
    Description = "",
    Callback = RefreshWeaponList
})

RefreshWeaponList()

local ToggleAutoEquiped = Tabs.Main:AddToggle("ToggleAutoEquiped", {Title = "Auto Equiped", Default = false })
ToggleAutoEquiped:OnChanged(function(a)
_G.AutoEquiped = a
end)





spawn(function()
while wait(.1) do
if _G.AutoEquiped then
pcall(function()
game.Players.LocalPlayer.Character.Humanoid:EquipTool(game:GetService("Players").LocalPlayer.Backpack:FindFirstChild(_G.SelectWeapon))
end)
end
end
end)



function TP(CFrame)
    pcall(function()
        game.Players.LocalPlayer.Character:WaitForChild("HumanoidRootPart").CFrame = CFrame
    end)
end


function checklevel()
    local lv = game:GetService("Players").LocalPlayer.PlayerStats.lvl.Value
    if lv == 0 or lv <= 9 then
        Mon = "Soldier [Lv. 1]"
        Title = "Soldier"
        QuestName = "QuestLvl0"
        CFrameQuest = CFrame.new(-1961, 49, -4499)
        CFrameMon = CFrame.new(-1885, 49, -4401)
    elseif lv == 10 or lv <= 19 then
        Mon = "Clown Pirate [Lv. 10]"
        Title = "Clown Pirate"
        QuestName = "QuestLvl10"
        CFrameQuest = CFrame.new(-1892.8999, 48.3011055, -4522.47607, 0.757697999, -2.2961677e-08, -0.652605355, 8.47295745e-09, 1, -2.5347223e-08, 0.652605355, 1.36760425e-08, 0.757697999)
        CFrameMon = CFrame.new(-1907.39453, 48.1856842, -4370.34912, -0.809620857, -6.63535147e-08, 0.586953163, 4.93648766e-09, 1, 1.19856566e-07, -0.586953163, 9.99358676e-08, -0.809620857)
    elseif lv == 20 or lv <= 29 then
        Mon = "Smoky [Lv. 20]"
        Title = "Smoky"
        QuestName = "QuestLvl20"
        CFrameQuest = CFrame.new(-1966.97852, 48.3011131, -4615.28613, -0.796190977, 4.69285899e-09, -0.605045378, -2.37740156e-08, 1, 3.90408985e-08, 0.605045378, 4.54683686e-08, -0.796190977)
        CFrameMon = CFrame.new(-1889.18689, 48.1977158, -4714.41162, -0.177651972, -2.9883207e-08, -0.984093368, 3.15410986e-09, 1, -3.09356238e-08, 0.984093368, -8.59971294e-09, -0.177651972)
    elseif lv == 30 or lv <= 49 then
        Mon = "Tashi [Lv. 30]"
        Title = "Tashi"
        QuestName = "QuestLvl30"
        CFrameQuest = CFrame.new(-2274.34741, 48.7510185, -4676.79736, 0.999449849, -9.75622694e-09, 0.033165805, 9.47501722e-09, 1, 8.63607585e-09, -0.033165805, -8.31707769e-09, 0.999449849)
        CFrameMon = CFrame.new(-2081.26025, 48.1924591, -4837.58154, 0.627375901, -1.40919756e-08, -0.778716564, -9.0752289e-10, 1, -1.88275617e-08, 0.778716564, 1.25186608e-08, 0.627375901)
        elseif lv == 50 or lv <= 74 then
        Mon = "Clown Swordman [Lv. 50]"
        Title = "Clown Swordman"
        QuestName = "QuestLvl50"
        CFrameQuest = CFrame.new(-681.433289, 37.9657364, -3464.35034, 0.718844354, 0, -0.695171058, 0, 1, 0, 0.695171058, 0, 0.718844354)
        CFrameMon = CFrame.new(-720.769653, 38.0411606, -3586.36865, 0.968808174, 0, 0.247811809, 0, 1, 0, -0.247811809, 0, 0.968808174)
    elseif lv == 75 or lv <= 99 then
        Mon = "The Clown [Lv. 75]"
        Title = "The Clown"
        QuestName = "QuestLvl75"
        CFrameQuest = CFrame.new(-391.532806, 68.9439774, -3495.65942, -0.987957001, 0, -0.154728606, 0, 1, 0, 0.154728606, 0, -0.987957001)
        CFrameMon = CFrame.new(-403.584106, 68.9954681, -3595.40576, 0.941231847, 4.3175068e-09, 0.337761134, -2.67921685e-09, 1, -5.31660493e-09, -0.337761134, 4.09922274e-09, 0.941231847)
    elseif lv == 100 or lv <= 119 then
        Mon = "Commander [Lv. 100]"
        Title = "Commander"
        QuestName = "QuestLvl100"
        CFrameQuest = CFrame.new(-2271.96533, 39.5081367, -2687.87329, -0.0437719822, 0, -0.999041557, 0, 1, 0, 0.999041557, 0, -0.0437719822)
        CFrameMon = CFrame.new(-2144.12622, 39.5835762, -2534.11426, -0.500952423, 0, -0.86547482, 0, 1, 0, 0.86547482, 0, -0.500952423)
    elseif lv == 120 or lv <= 144 then
        Mon = "Captain [Lv. 120]"
        Title = "Captain"
        QuestName = "QuestLvl120"
        CFrameQuest = CFrame.new(-2271.96533, 39.5081367, -2687.87329, -0.0437719822, 0, -0.999041557, 0, 1, 0, 0.999041557, 0, -0.0437719822)
        CFrameMon = CFrame.new(-2144.12622, 39.5835762, -2534.11426, -0.500952423, 0, -0.86547482, 0, 1, 0, 0.86547482, 0, -0.500952423)
    elseif lv == 145 or lv <= 249 then
        Mon = "The Barbaric [Lv. 145]"
        Title = "The Barbaric"
        QuestName = "QuestLvl145"
        CFrameQuest = CFrame.new(-2463.1189, 68.7791901, -2541.75562, -0.985592782, 0, 0.169135571, 0, 1, 0, -0.169135571, 0, -0.985592782)
        CFrameMon = CFrame.new(-2338.21313, 68.8122253, -2500.81372, -0.579432607, 0, -0.815020144, 0, 1, 0, 0.815020144, 0, -0.579432607)
    elseif lv == 250 or lv <= 299 then
        Mon = "Trainer Chef [Lv. 250]"
        Title = "Trainer Chef"
        QuestName = "QuestLvl250"
        CFrameQuest = CFrame.new(-4095.83105, 64.2309723, -3019.66772, 0.0543251261, 0, -0.998523295, 0, 1, 0, 0.998523295, 0, 0.0543251261)
        CFrameMon = CFrame.new(-4016.52783, 15.3243008, -3137.3562, 0.953339219, 0, 0.301901162, 0, 1, 0, -0.301901162, 0, 0.953339219)
    elseif lv == 300 or lv <= 349 then
        Mon = "Dark Leg [Lv. 300]"
        Title = "Dark Leg"
        QuestName = "QuestLvl300"
        CFrameQuest = CFrame.new(-4197.30908, 64.2310333, -3028.89893, -0.969855011, 0, -0.243682623, 0, 1, 0, 0.243682623, 0, -0.969855011)
        CFrameMon = CFrame.new(-4216.90186, 18.0548019, -2876.38794, -0.881443918, 0, 0.472288758, 0, 1, 0, -0.472288758, 0, -0.881443918)
        elseif lv == 350 or lv <= 399 then
        Mon = "Dory [Lv. 350]"
        Title = "Dory"
        QuestName = "QuestLvl350"
        CFrameQuest = CFrame.new(-4405.32617, 65.1222763, -2943.86084, -0.88148576, 0, 0.472210586, 0, 1, 0, -0.472210586, 0, -0.88148576)
        CFrameMon = CFrame.new(-4435.08301, 15.340682, -2616.44434, 0.994279206, 0, 0.106812403, 0, 1, 0, -0.106812403, 0, 0.994279206)
    elseif lv == 400 or lv <= 449 then
        Mon = "Snow Soldier [Lv. 400]"
        Title = "Snow Soldier"
        QuestName = "QuestLvl400"
        CFrameQuest = CFrame.new(-5461.93457, 18.2433815, -1342.39233, -0.822549045, 0, -0.568694174, 0, 1, 0, 0.568694174, 0, -0.822549045)
        CFrameMon = CFrame.new(-5305.4082, 19.6430225, -1311.98035, 0.550353229, 0, -0.83493185, 0, 1.00000012, 0, 0.83493197, 0, 0.550353169)
    elseif lv == 450 or lv <= 499 then
        Mon = "King Snow [Lv. 450]"
        Title = "King Snow"
        QuestName = "QuestLvl450"
        CFrameQuest = CFrame.new(-5540.55762, 18.0411034, -1476.93213, 0.832889795, 4.09659684e-09, 0.553438842, -3.99380884e-09, 1, -1.39165179e-09, -0.553438842, -1.05123621e-09, 0.832889795)
        CFrameMon = CFrame.new(-5509.18994, 17.9336624, -1654.82214, 0.905777156, -6.65005695e-09, 0.423754334, -8.89691376e-10, 1, 1.75949086e-08, -0.423754334, -1.63140772e-08, 0.905777156)
    elseif lv == 500 or lv <= 524 then
        Mon = "Little Dear [Lv. 500]"
        Title = "Little Dear"
        QuestName = "QuestLvl500"
        CFrameQuest = CFrame.new(-5301.22656, 17.9285564, -1099.28259, -0.854913652, 5.95215361e-08, 0.518770337, 2.16574545e-08, 1, -7.9045158e-08, -0.518770337, -5.63415377e-08, -0.854913652)
        CFrameMon = CFrame.new(-5201.09326, 11.7197084, -1079.57312, -0.236631855, 5.53104336e-08, -0.9715994, -1.42908219e-09, 1, 5.72752512e-08, 0.9715994, 1.49416444e-08, -0.236631855)
    elseif lv == 525 or lv <= 624 then
        Mon = "Candle Man [Lv. 525]"
        Title = "Candle Man"
        QuestName = "QuestLvl500"
        CFrameQuest = CFrame.new(-2731.91357, 14.9978447, -598.363281, -0.0577159226, -5.38591252e-08, 0.998333037, 8.58933991e-09, 1, 5.44456249e-08, -0.998333037, 1.17174013e-08, -0.0577159226)
        CFrameMon = CFrame.new(-2661.06763, 13.0811539, -659.510254, 0.997233689, -1.09273497e-08, 0.0743301883, 1.26810331e-08, 1, -2.31212134e-08, -0.0743301883, 2.39998368e-08, 0.997233689)
    elseif lv == 625 or lv <= 724 then
        Mon = "Bomb Man [Lv. 625]"
        Title = "Bomb Man"
        QuestName = "QuestLvl625"
        CFrameQuest = CFrame.new(-2946.58667, 16.7614727, -806.553528, -0.963528514, 8.57098073e-08, 0.267605603, 8.60052083e-08, 1, -1.06176152e-08, -0.267605603, 1.27851001e-08, -0.963528514)
        CFrameMon = CFrame.new(-2898.03784, 13.0688343, -894.140442, 0.154548734, -7.69490427e-09, -0.987985194, 3.09271553e-10, 1, -7.74010278e-09, 0.987985194, 8.90667429e-10, 0.154548734)
    elseif lv == 725 or lv <= 799 then
        Mon = "King of Sand [Lv. 725]"
        Title = "King of Sand"
        QuestName = "QuestLvl725"
        CFrameQuest = CFrame.new(-2947.60645, 43.1564789, -700.18988, 0.276689172, 2.20242296e-08, 0.960959494, -9.73630176e-10, 1, -2.26386625e-08, -0.960959494, 5.32825339e-09, 0.276689172)
        CFrameMon = CFrame.new(-3118.73193, 97.2251282, -487.598724, -0.711142361, -5.80723487e-08, 0.70304805, -6.11243145e-09, 1, 7.64180257e-08, -0.70304805, 5.00467614e-08, -0.711142361)
        elseif lv == 800 or lv <= 849 then
        Mon = "Sky Soldier"
        Title = "Sky Soldier"
        QuestName = "QuestLvl800"
        CFrameQuest = CFrame.new(-4484.00488, 200.854172, 1038.93018, 0.608264029, -6.9889353e-08, 0.793734729, 3.45996582e-08, 1, 6.15364613e-08, -0.793734729, -9.96746508e-09, 0.608264029)
        CFrameMon = CFrame.new(-4609.3584, 222.532639, 1213.96643, -0.950836897, -2.32851853e-08, 0.309692055, -3.13842374e-09, 1, 6.5552392e-08, -0.309692055, 6.13576887e-08, -0.950836897)
    elseif lv == 850 or lv <= 899 then
        Mon = "Ball Man [Lv. 850]"
        Title = "Ball Man"
        QuestName = "QuestLvl850"
        CFrameQuest = CFrame.new(-4044.60742, 387.458649, 1209.44836, 0.935271323, 2.28931185e-08, 0.353931576, -3.74928284e-08, 1, 3.43932207e-08, -0.353931576, -4.5436888e-08, 0.935271323)
        CFrameMon = CFrame.new(-3974.33813, 386.643982, 1282.48364, -0.713762403, 2.99211855e-08, -0.700387895, -4.10975431e-08, 1, 8.46032151e-08, 0.700387895, 8.91708112e-08, -0.713762403)
    elseif lv == 900 or lv <= 1249 then
        Mon = "Rumble Man [Lv. 900]"
        Title = "Rumble Man"
        QuestName = "QuestLvl900"
        CFrameQuest = CFrame.new(-4092.9248, 386.592255, 1343.92688, 0.706490755, 0, -0.707722306, 0, 1, 0, 0.707722306, 0, 0.706490755)
        CFrameMon = CFrame.new(-4167.53027, 386.641266, 1523.5813, -0.934745848, 0, -0.355317086, 0, 1, 0, 0.355317086, 0, -0.934745848)
    elseif lv == 1250 or lv <= 1324 then
        Mon = "Wolf [Lv. 1250]"
        Title = "Wolf"
        QuestName = "QuestLvl1250"
        CFrameQuest = CFrame.new(-1247.07471, 13.202426, 2181.41431, 0.801206291, 0, 0.598388255, 0, 1, 0, -0.598388255, 0, 0.801206291)
        CFrameMon = CFrame.new(-1336.15942, 13.2519121, 2221.44971, 0.140932292, 0, 0.990019262, 0, 1, 0, -0.990019262, 0, 0.140932292)
    elseif lv == 1325 or lv <= 1399 then
        Mon = "Giraffe [Lv. 1325]"
        Title = "Giraffe"
        QuestName = "QuestLvl1325<"
        CFrameQuest = CFrame.new(-1192.27307, 13.202426, 2216.28198, 0.422244608, 0, -0.906481922, 0, 1, 0, 0.906481922, 0, 0.422244608)
        CFrameMon = CFrame.new(-1082.92468, 13.202426, 2268.76123, 0.05387922, 5.25465671e-09, -0.998547435, -2.72804144e-08, 1, 3.79031473e-09, 0.998547435, 2.70365685e-08, 0.05387922)
    elseif lv == 1400 or lv <= 1499 then
        Mon = "Leo [Lv. 1400]"
        Title = "Leo [Lv. 1400]"
        QuestName = "QuestLvl1400"
        CFrameQuest = CFrame.new(-1120.35901, 13.1328764, 2845.11133, -0.540736675, 0, -0.841191947, 0, 1, 0, 0.841191947, 0, -0.540736675)
        CFrameMon = CFrame.new(-1136.99915, 13.1826534, 2940.25854, -0.999186277, 0, 0.0403332077, 0, 1, 0, -0.0403332077, 0, -0.999186277)
    elseif lv == 1500 or lv <= 1599 then
        Mon = "Zombie [Lv. 1500]"
        Title = "Zombie"
        QuestName = "QuestLvl1500"
        CFrameQuest = CFrame.new(-2732.90747, 15.922823, 4083.07861, 0.1971706, 0, 0.98036921, 0, 1, 0, -0.98036921, 0, 0.1971706)
        CFrameMon = CFrame.new(-2774.32251, 15.922823, 4095.25439, -0.586313665, 0, 0.810084105, 0, 1, 0, -0.810084105, 0, -0.586313665)
        elseif lv == 1600 or lv <= 1699 then
        Mon = "Shadow Master [Lv. 1600]"
        Title = "Shadow Master"
        QuestName = "QuestLvl1600"
        CFrameQuest = CFrame.new(-2792.16919, 18.7855186, 4231.1167, -0.882326841, 0, -0.470637172, 0, 1, 0, 0.470637172, 0, -0.882326841)
        CFrameMon = CFrame.new(-2846.33936, 20.1586838, 4289.14404, -0.953912258, 0, 0.300085753, 0, 1, 0, -0.300085753, 0, -0.953912258)
    elseif lv == 1700 or lv <= 1799 then
        Mon = "New World Pirate [Lv. 1700]"
        Title = "New World Pirate"
        QuestName = "QuestLvl1700"
        CFrameQuest = CFrame.new(2391.98486, 49.7537041, -1781.72351, -0.363805652, 0, -0.931474864, 0, 1, 0, 0.931474864, 0, -0.363805652)
        CFrameMon = CFrame.new(2288.72314, 49.7766533, -1666.77136, -0.971531034, 0, 0.23691231, 0, 1, 0, -0.23691231, 0, -0.971531034)
    elseif lv == 1800 or lv <= 1924 then
        Mon = "Rear Admiral [Lv. 1800]"
        Title = "Rear Admiral [Lv. 1800]"
        QuestName = "QuestLvl1800"
        CFrameQuest = CFrame.new(2399.54395, 49.8040428, -2236.3269, 0.597588181, 0, -0.801803231, 0, 1, 0, 0.801803231, 0, 0.597588181)
        CFrameMon = CFrame.new(2299.59692, 49.7666359, -2240.53638, 0.0972526222, 0, 0.995259702, 0, 1, 0, -0.995259702, 0, 0.0972526222)
    elseif lv == 1925 or lv <= 1999 then
        Mon = "Quake Woman [Lv. 1925]"
        Title = "Quake Woman"
        QuestName = "QuestLvl1925"
        CFrameQuest = CFrame.new(2117.63843, 49.4552956, -2116.6626, 0.999964595, -1.40285561e-08, 0.00841410644, 1.36683109e-08, 1, 4.2871946e-08, -0.00841410644, -4.27554205e-08, 0.999964595)
        CFrameMon = CFrame.new(2182.77881, 2.89610672, -1925.16638, -0.929547846, -1.72607262e-08, -0.368701518, -4.38146019e-10, 1, -4.57102765e-08, 0.368701518, -4.23283453e-08, -0.929547846)
    elseif lv == 2000 or lv <= 2049 then
        Mon = "Fishman [Lv. 2000]"
        Title = "Fishman"
        QuestName = "QuestLvl2000"
        CFrameQuest = CFrame.new(-1467.42493, 40.4170723, 6221.82568, -0.942648709, 5.96108833e-08, -0.333786488, 8.06639591e-08, 1, -4.92137744e-08, 0.333786488, -7.33158387e-08, -0.942648709)
        CFrameMon = CFrame.new(-1599.41711, 40.5421333, 6173.11914, 0.479094267, -2.64866848e-08, 0.87776345, 2.1916049e-09, 1, 2.89789917e-08, -0.87776345, -1.19599584e-08, 0.479094267)
        elseif lv == 2050 or lv <= 2149 then
        Mon = "Combat Fishman [Lv. 2050]"
        Title = "Combat Fishman"
        QuestName = "QuestLvl2050"
        CFrameQuest = CFrame.new(-1925.26294, 40.1034966, 6266.82178, 0.803146482, -4.24684554e-09, 0.595781624, 4.47117232e-09, 1, 1.10080534e-09, -0.595781624, 1.77973425e-09, 0.803146482)
        CFrameMon = CFrame.new(-1931.40344, 40.2257805, 6161.25293, 0.980371952, 3.34984058e-08, 0.197156832, -2.07475299e-08, 1, -6.67393039e-08, -0.197156832, 6.13388238e-08, 0.980371952)
    elseif lv == 2150 or lv <= 2199 then
        Mon = "Soldier Fishman [Lv. 2150]"
        Title = "Soldier Fishman"
        QuestName = "QuestLvl2150"
        CFrameQuest = CFrame.new(-1770.03699, 40.4459038, 6493.48047, -0.947936416, 2.22029684e-08, 0.3184596, -1.3315975e-08, 1, -1.0935662e-07, -0.3184596, -1.07903723e-07, -0.947936416)
        CFrameMon = CFrame.new(-1833.03918, 45.3223572, 6602.22607, -0.971651137, 1.33137584e-10, 0.236419171, -3.89461463e-10, 1, -2.16377671e-09, -0.236419171, -2.19451213e-09, -0.971651137)
    elseif lv == 2200 or lv <= 45000 then
        Mon = "Seasoned Fishman [Lv. 2200]"
        Title = "Seasoned Fishman"
        QuestName = "QuestLvl2200"
        CFrameQuest = CFrame.new(-1919.16125, 40.4427223, 6473.93213, -0.900462687, 0, 0.434933305, 0, 1, 0, -0.434933305, 0, -0.900462687)
        CFrameMon = CFrame.new(-1851.30005, 45.3223572, 6646.06396, -0.993926764, 0, 0.110043757, 0, 1, 0, -0.110043757, 0, -0.993926764)
    end
end

function Click()
    local VirtualUser = game:GetService('VirtualUser')
    VirtualUser:CaptureController()
    VirtualUser:ClickButton1(Vector2.new(851, 158), game:GetService("Workspace").Camera.CFrame)
end

spawn(function()
    while true do
        if _G.Auto_Farm then
            checklevel()
            if game.Players.LocalPlayer.PlayerGui.MainGui.QuestBoard.Visible == false then 
                TP(CFrameQuest)
                wait(0.3)
                local args = {
                    [1] = workspace:WaitForChild("AllNPC"):WaitForChild(QuestName)
                }
                game:GetService("ReplicatedStorage"):WaitForChild("Chest"):WaitForChild("Remotes"):WaitForChild("Functions"):WaitForChild("CheckQuest"):InvokeServer(unpack(args))
            elseif game.Players.LocalPlayer.PlayerGui.MainGui.QuestBoard.Visible == true then 
                for _,v in ipairs(game.Workspace.Monster.Mon:GetChildren()) do
                    if v.Name == Mon then
                        local humanoid = v:FindFirstChildOfClass("Humanoid")
                        if humanoid and humanoid.Health > 0 then
                            TP(v.HumanoidRootPart.CFrame*MethodFarm)
                            Click()
                            AT()
                            Attack()
                        end
                    end
                end
            end
        end
        wait(0.1) -- แก้ไขการเรียกใช้ wait จาก task.wait
    end
end)

spawn(function()
    while true do
        if _G.Auto_Farm then
            checklevel()
            for _,v in ipairs(game.Workspace.Monster.Mon:GetChildren()) do
                if v.Name == Mon then
                    local humanoid = v:FindFirstChildOfClass("Humanoid")
                    if humanoid and humanoid.Health == 0 then
                        v:Destroy()
                    end
                end
            end
        end
        wait(0.1) -- แก้ไขการเรียกใช้ wait จาก task.wait
    end
end)

function AT()
local args = {
    [1] = "SW_" .. _G.SelectWeapon .. "_M1"
}

game:GetService("ReplicatedStorage"):WaitForChild("Chest"):WaitForChild("Remotes"):WaitForChild("Functions"):WaitForChild("SkillAction"):InvokeServer(unpack(args))
end


function Attack()
	wait()
	local args = {
    [1] = "FS_" .. _G.SelectWeapon .. "_M1"
}

game:GetService("ReplicatedStorage").Chest.Remotes.Functions.SkillAction:InvokeServer(unpack(args))
end

spawn(function()
    while true do
        if _G.Boss then
            checklevel()
            if game.Players.LocalPlayer.PlayerGui.MainGui.QuestBoard.Visible == false then 
                TP(CFrameQuest)
                wait(0.3)
                local args = {
                    [1] = workspace:WaitForChild("AllNPC"):WaitForChild(QuestName)
                }
                game:GetService("ReplicatedStorage"):WaitForChild("Chest"):WaitForChild("Remotes"):WaitForChild("Functions"):WaitForChild("CheckQuest"):InvokeServer(unpack(args))
            elseif game.Players.LocalPlayer.PlayerGui.MainGui.QuestBoard.Visible == true then 
                for _,v in ipairs(game.Workspace.Monster.Boss:GetChildren()) do
                if v.Name == Mon then
                        local humanoid = v:FindFirstChildOfClass("Humanoid")
                        if humanoid and humanoid.Health > 0 then
                            TP(v.HumanoidRootPart.CFrame*MethodFarm)
                            Click()
                            AT() -- แก้ไขการเรียกใช้ฟังก์ชัน Click ที่เพิ่มเข้ามา
                            Attack()
                        end
                    end
                end
            end
        end
        wait(0.1) -- แก้ไขการเรียกใช้ wait จาก task.wait
    end
end)
 



spawn(function()
    while true do
        if _G.Boss then
            checklevel()
            for _,v in ipairs(game.Workspace.Monster.Boss:GetChildren()) do
                if v.Name == Mon then
                    local humanoid = v:FindFirstChildOfClass("Humanoid")
                    if humanoid and humanoid.Health == 0 then
                        v:Destroy()
                    end
                end
            end
        end
        wait(0.1) -- แก้ไขการเรียกใช้ wait จาก task.wait
    end
end)



    


spawn(function()
    game:GetService("RunService"):UnbindFromRenderStep("noclOppl")
    game:GetService("RunService"):BindToRenderStep("noclOppl",0,function()
        if _G.Auto_Farm then -- แก้ไขการเรียกใช้ตัวแปรจาก SaveSettings เป็น _G.Auto_Farm
            pcall(function()
                for i2,v in pairs(game.Players.LocalPlayer.PlayerGui:GetChildren()) do -- แก้ไขการเรียกใช้ตัวแปร plr เป็น game.Players.LocalPlayer
                    if string.find(v.Name, QuestName) or string.find(v.Name, "SwordShop") then 
                        v.Dialogue.Accept.Position = UDim2.new(0, -800 ,0, -700)
                        v.Dialogue.Accept.Size = UDim2.new(5000, 5000, 5000, 5000)
                        v.Dialogue.Accept.BackgroundTransparency = 1
                        v.Dialogue.Accept.ImageTransparency = 1
                        Click() -- แก้ไขการเรียกใช้ฟังก์ชัน Click ที่เพิ่มเข้ามา
                    end
                end
            end)
        end
    end)
end)


Tabs.Teleport:AddParagraph({
    Title = "Island",
    Content = "Teleport to Island"
})

 IslandList = {
                "ZombieIsland",
                "WarIsland",
                "Tundar",
                "StoneArena",
                "StarterIsland",
                "SoldierIsland",
                "SkyIsland",
                "SharkIsland",
                "Sea of dust",
                "RainyStone",
                "PirateIsland",
                "LobbyIsland",
                "Fishland",
                "ChefShip",
                "Bubble",
}
local DropdownIsland = Tabs.Teleport:AddDropdown("DropdownIsland",{
    Title = "Select lsland",
    Values = IslandList,
    Multi = false,
    Default = 1,
})

DropdownIsland:SetValue("...")
DropdownIsland:OnChanged(function(Value)
    _G.SelectIsland = Value
end)

local ToggleIsland = Tabs.Teleport:AddToggle("ToggleIsland", {Title = "Teleport Island", Default = false })
ToggleIsland:OnChanged(function(Value)
    _G.TeleportIsland = Value
    if _G.TeleportIsland == true then
        repeat wait()
            if _G.SelectIsland == "ZombieIsland" then
                TP(CFrame.new(-2840.63892, 16.9892197, 4201.29395, 0.510093927, 4.72610076e-08, 0.860118687, 3.05605532e-08, 1, -7.30710354e-08, -0.860118687, 6.35587938e-08, 0.510093927

)) 
            elseif _G.SelectIsland == "WarIsland" then
                TP(CFrame.new(2270.54199, 11.2288952, -1925.93005, 0.00962084439, 1.54562514e-08, 0.999953747, 2.0645551e-08, 1, -1.5655603e-08, -0.999953747, 2.07952162e-08, 0.00962084439))
                elseif _G.SelectIsland == "Tundar" then
                TP(CFrame.new(-5462.70508, 17.9270401, -1294.78796, 0.976918578, 6.50538752e-08, 0.213612095, -4.48596218e-08, 1, -9.9384259e-08, -0.213612095, 8.75077717e-08, 0.976918578))
                elseif _G.SelectIsland == "StoneArena" then
                TP(CFrame.new(5458.87207, 37.577446, -6614.98486, 0.929369867, 4.9416176e-08, -0.369149864, -7.04594143e-08, 1, -4.35234639e-08, 0.369149864, 6.64594779e-08, 0.929369867))
                elseif _G.SelectIsland == "StarterIsland" then
                TP(CFrame.new(-2032.13196, 48.1566849, -4635.61279, 0.785932064, -3.06101278e-08, 0.618312836, -1.39465761e-09, 1, 5.12786258e-08, -0.618312836, -4.1163851e-08, 0.785932064))
                elseif _G.SelectIsland == "SoldierIsland" then
                TP(CFrame.new(-2358.14795, 68.4404297, -2596.41211, 0.45018369, 2.11132711e-09, 0.892935991, -1.53912136e-08, 1, 5.39517497e-09, -0.892935991, -1.61721871e-08, 0.45018369))
                elseif _G.SelectIsland == "SkyIsland" then
                TP(CFrame.new(-4277.35498, 377.675049, 1234.901, -0.140449286, 7.7489446e-08, 0.990087867, -9.83279769e-09, 1, -7.96600546e-08, -0.990087867, -2.09235314e-08, -0.140449286)))
                elseif _G.SelectIsland == "SharkIsland" then
                TP(CFrame.new(-603.536011, 10.297368, -1448.53796, 0.560506225, 1.07520272e-07, 0.828150213, -8.42996641e-08, 1, -7.27763947e-08, -0.828150213, -2.90211641e-08, 0.560506225))
                elseif _G.SelectIsland == "Sea of dust" then
                TP(CFrame.new(-2892.57397, 42.8405151, -630.768982, -0.730246425, -5.20490673e-09, -0.683183849, -4.76044049e-09, 1, -2.53022958e-09, 0.683183849, 1.40456502e-09, -0.730246425))
                elseif _G.SelectIsland == "RainyStone" then
                TP(CFrame.new(2017.20276, 208.72522, -4850.34521, -0.90416348, -2.78546342e-08, -0.427186579, -1.4972894e-08, 1, -3.35139063e-08, 0.427186579, -2.39058302e-08, -0.90416348)))
                elseif _G.SelectIsland == "PirateIsland" then
                TP(CFrame.new(-585.096985, 37.6493835, -3465.64209, 0.840984821, 2.9174668e-08, 0.541058719, -9.53016244e-09, 1, -3.91084107e-08, -0.541058719, 2.77332024e-08, 0.840984821))
                elseif _G.SelectIsland == "LobbyIsland" then
                TP(CFrame.new(-1210.73206, 12.9459019, 2193.302, 0.996385217, 1.01098685e-08, 0.0849503055, -9.25709465e-09, 1, -1.04324114e-08, -0.0849503055, 9.60830704e-09, 0.996385217))
                elseif _G.SelectIsland == "Fishland" then
                TP(CFrame.new(-1706.23804, 40.1007233, 6395.58691, 0.989434302, 1.013432e-09, 0.144981787, -8.63037197e-10, 1, -1.10023046e-09, -0.144981787, 9.63481073e-10, 0.989434302))
                elseif _G.SelectIsland == "ChefShip" then
                TP(CFrame.new(-4300.76025, 108.411507, -2952.02295, -0.81242913, -1.74138322e-08, -0.583059967, -4.49295001e-09, 1, -2.3605855e-08, 0.583059967, -1.65584257e-08, -0.81242913))
                elseif _G.SelectIsland == "Bubble" then
                TP(CFrame.new(1653.20178, 12.071167, 653.67334, 0.276743919, 3.96236421e-09, 0.960943699, -2.1127522e-09, 1, -3.51495411e-09, -0.960943699, -1.05749376e-09, 0.276743919))
            end
        until not _G.TeleportIsland
    end
end)
Options.ToggleIsland:SetValue(false)



-- Addons:

-- SaveManager (Allows you to have a configuration system)

-- InterfaceManager (Allows you to have a interface managment system)

-- Hand the library over to our managers
SaveManager:SetLibrary(Fluent)
InterfaceManager:SetLibrary(Fluent)

-- Ignore keys that are used by ThemeManager.
-- (we dont want configs to save themes, do we?)
SaveManager:IgnoreThemeSettings()

-- You can add indexes of elements the save manager should ignore
SaveManager:SetIgnoreIndexes({})

-- use case for doing it this way:
-- a script hub could have themes in a global folder
-- and game configs in a separate folder per game
InterfaceManager:SetFolder("ZAHUB")
SaveManager:SetFolder("ZAHUB/KLMain")

InterfaceManager:BuildInterfaceSection(Tabs.Settings)
SaveManager:BuildConfigSection(Tabs.Settings)


Window:SelectTab(1)



local ScreenGui1 = Instance.new("ScreenGui")
local ImageButton1 = Instance.new("ImageButton")
local UICorner = Instance.new("UICorner")

ScreenGui1.Name = "ImageButton"
ScreenGui1.Parent = game.CoreGui
ScreenGui1.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

ImageButton1.Parent = ScreenGui1
ImageButton1.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ImageButton1.BorderSizePixel = 0
ImageButton1.Position = UDim2.new(0.120833337, 0, 0.0952890813, 0)
ImageButton1.Size = UDim2.new(0, 50, 0, 50)
ImageButton1.Draggable = true
ImageButton1.Image = "http://www.roblox.com/asset/?id=16492784848"
ImageButton1.MouseButton1Down:connect(function()
  game:GetService("VirtualInputManager"):SendKeyEvent(true,305,false,game)
  game:GetService("VirtualInputManager"):SendKeyEvent(false,305,false,game)
end)
UICorner.Parent = ImageButton1

do local GUI = game.CoreGui:FindFirstChild("SOMEXHUB");if GUI then GUI:Destroy();end;if _G.Color == nil then
    _G.Color = Color3.fromRGB(230, 5, 12)
   end 
end









SaveManager:LoadAutoloadConfig()



Input:OnChanged(function()
        print("Input updated:", Input.Value)
    end)
end
