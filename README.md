# UE4-5 Stutter-Fix 🐨
Unreal Engine 4 - 5 Stutter Fix
1 - Go to your file explorer and paste the following: C:\Users\%username%\AppData\Local

2 - Now find the name of your game or the name of the developer/publisher of the game

3 - After that go into Saved > Config > WindowsClient or WindowsNoEditor or WinGDK (whichever one appears) then open up Engine.ini

4 - Copy the commands from one of the txt files in this repo below then paste them at the bottom of the Engine.ini file then save (Some games will automatically remove the commands. If this happens right click > Properties > General > Read-only)

I recommend trying high first as low looks bad but its the only way to fix the issue on low end systems or stubborn games (like 3gb GPUs)

Here are some additional commands to include. I excluded them because some games crashed when they were enabled but they do help

[/Script/Engine.RendererSettings]
```
r.CreateShadersOnLoad=1
r.HZBOcclusion=2
r.SkinCache.CompileShaders=1
General Tweaks
```
1 - Select DX12/Vulkan > DX11 ingame if it is a supported rendering API (In that order, from best to worse. Most of the time anyway)

2 - Disable overlays (GeForce Experience, Steam, etc) not every game will suffer from stuttering with overlays but a lot of big popular games still do as it messes with GPU utilization

Steam Tweaks
If your game is on Steam right click it, click on properties then in the "Launch Options" field paste the following

Low VRAM
```
-xgeshadercompile -nothreadtimeout
```
8GB+ VRAM
```
-xgeshadercompile -nothreadtimeout -NoVerifyGC
```
DX11 Game (Forcing DX12)
```
-force -dx12
```
DX11 Game (Staying in DX11 / Forcing DX12 doesn't work)
```
-norhithread
```
