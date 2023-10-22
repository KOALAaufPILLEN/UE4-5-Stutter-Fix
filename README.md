# UE4-5 Stutter-Fix 🐨

![koala](https://github.com/KOALAaufPILLEN/UE4-5-Stutter-Fix/assets/92574026/5c2ae6c1-4ab4-47f2-bc28-6c83f96a6d80)
# Unreal Engine 4 - 5 Stutter Fix

This guide provides instructions on how to fix stuttering issues in Unreal Engine 4 - 5 games. Follow the steps below to resolve stuttering and improve performance.

## Instructions

1. Go to your file explorer and navigate to the following location: `C:\Users\%username%\AppData\Local`.

2. Find the folder with the name of your game or the name of the game's developer/publisher.

3. Inside that folder, navigate to `Saved > Config > WindowsClient` or `WindowsNoEditor` or `WinGDK` (whichever one appears). Open the `Engine.ini` file.

4. Copy the commands from one of the `.txt` files provided in this repository and paste them at the bottom of the `Engine.ini` file. Save the changes. Note that some games may automatically remove these commands. If this happens, right-click on the `Engine.ini` file, go to Properties > General, and ensure that the file is not set to Read-only.

## Additional Recommendations

- Start by trying the `high` preset for optimal visual quality. However, if you are experiencing stuttering on low-end systems or with stubborn games (e.g., running on 3GB GPUs), you may need to use the `low` preset.

- For further improvement, you can include the following additional commands in the `Engine.ini` file under the `[Script/Engine.RendererSettings]` section. Please note that enabling these commands may cause some games to crash, so use them with caution:

    ```
    r.CreateShadersOnLoad=1
    r.HZBOcclusion=2
    r.SkinCache.CompileShaders=1
    ```

## General Tweaks

1. In the game's graphics settings, select DX12/Vulkan if available, as they generally provide better performance compared to DX11.

2. Disable overlays from programs like GeForce Experience, Steam, etc. These overlays can interfere with GPU utilization and cause stuttering in some games.

## Steam Tweaks

If your game is on Steam, follow these additional steps:

- Right-click on the game and select Properties.
- Go to the "Launch Options" field and paste the appropriate command based on your VRAM size and desired rendering API:

    For Low VRAM:
    ```
    -xgeshadercompile -nothreadtimeout
    ```

    For 8GB+ VRAM:
    ```
    -xgeshadercompile -nothreadtimeout -NoVerifyGC
    ```

    For DX11 Games (Forcing DX12):
    ```
    -force -dx12
    ```

    For DX11 Games (Staying in DX11 / Forcing DX12 doesn't work):
    ```
    -norhithread
    ```

Please note that these tweaks may vary depending on the specific game and system configuration. Apply them cautiously and test the changes to ensure stability and optimal performance.

Remember to back up any files before making changes.

### Disclaimer
- This batch script is provided as-is and without warranty. Use it at your own risk. The author and the organization behind this script shall not be held responsible for any damages or issues arising from its usage.
If you encounter any issues or have further questions, please feel free to reach out for assistance.
