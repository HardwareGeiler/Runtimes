**1. Frameworks** (Credits to [Syrusaki](https://github.com/Syrusaki) )

echo Installing NetFramework 4.81...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.microsoft.com/download/4/b/2/cd00d4ed-ebdd-49ee-8a33-eabc3d1030e3/NDP481-x86-x64-AllOS-ENU.exe' -OutFile 'C:\NDP481-x86-x64-AllOS-ENU.exe'
start /wait C:\NDP481-x86-x64-AllOS-ENU.exe /Q
del /F /Q C:\NDP481-x86-x64-AllOS-ENU.exe
cls

echo Installing NetFramework 5 x64...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/3aa4e942-42cd-4bf5-afe7-fc23bd9c69c5/64da54c8864e473c19a7d3de15790418/windowsdesktop-runtime-5.0.17-win-x64.exe' -OutFile 'C:\windowsdesktop-runtime-5.0.17-win-x64.exe'
start /wait C:\windowsdesktop-runtime-5.0.17-win-x64.exe /Q
del /F /Q C:\windowsdesktop-runtime-5.0.17-win-x64.exe
cls

echo Installing NetFramework 5 x86...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/b6fe5f2a-95f4-46f1-9824-f5994f10bc69/db5ec9b47ec877b5276f83a185fdb6a0/windowsdesktop-runtime-5.0.17-win-x86.exe' -OutFile 'C:\windowsdesktop-runtime-5.0.17-win-x86.exe'
start /wait C:\windowsdesktop-runtime-5.0.17-win-x86.exe /Q
del /F /Q C:\windowsdesktop-runtime-5.0.17-win-x86.exe
cls

echo Installing NetFramework 6 x64...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/3ef3cd0c-8c7f-4146-bd8d-589d748b997e/3477d059f8fe5cceb5166b367d7995c6/windowsdesktop-runtime-6.0.27-win-x64.exe' -OutFile 'C:\windowsdesktop-runtime-6.0.27-win-x64.exe'
start /wait C:\windowsdesktop-runtime-6.0.27-win-x64.exe /Q
del /F /Q C:\windowsdesktop-runtime-6.0.27-win-x64.exe
cls

echo Installing NetFramework 6 x86...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/a9669480-f3e0-42a6-b381-108950dfe290/b54d6613c0fa2839c41d61478926ccb9/windowsdesktop-runtime-6.0.27-win-x86.exe' -OutFile 'C:\windowsdesktop-runtime-6.0.27-win-x86.exe'
start /wait C:\windowsdesktop-runtime-6.0.27-win-x86.exe /Q
del /F /Q C:\windowsdesktop-runtime-6.0.27-win-x86.exe
cls

echo Installing NetFramework 7 x64...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/38c809cc-858d-45ed-88f5-a7f098cab691/2e4f859f8f6cf64aa952df2a80f16d2e/windowsdesktop-runtime-7.0.16-win-x64.exe' -OutFile 'C:\windowsdesktop-runtime-7.0.16-win-x64.exe'
start /wait C:\windowsdesktop-runtime-7.0.16-win-x64.exe /Q
del /F /Q C:\windowsdesktop-runtime-7.0.16-win-x64.exe
cls

echo Installing NetFramework 7 x84...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/ff4b13ba-07aa-4aa7-b5ae-9111c363c802/5fdedee9a9fae645bfdda3a8930c923d/windowsdesktop-runtime-7.0.16-win-x86.exe' -OutFile 'C:\windowsdesktop-runtime-7.0.16-win-x86.exe'
start /wait C:\windowsdesktop-runtime-7.0.16-win-x86.exe /Q
del /F /Q C:\windowsdesktop-runtime-7.0.16-win-x86.exe
cls

echo Installing NetFramework 8 x64...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/84ba33d4-4407-4572-9bfa-414d26e7c67c/bb81f8c9e6c9ee1ca547396f6e71b65f/windowsdesktop-runtime-8.0.2-win-x64.exe' -OutFile 'C:\windowsdesktop-runtime-8.0.2-win-x64.exe'
start /wait C:\windowsdesktop-runtime-8.0.2-win-x64.exe /Q
del /F /Q C:\windowsdesktop-runtime-8.0.2-win-x64.exe
cls

echo Installing NetFramework 8 x86...
timeout /t 2 >nul
powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/9b77b480-7e32-4321-b417-a41e0f8ea952/3922bbf5538277b1d41e9b49ee443673/windowsdesktop-runtime-8.0.2-win-x86.exe' -OutFile 'C:\windowsdesktop-runtime-8.0.2-win-x86.exe'
start /wait C:\windowsdesktop-runtime-8.0.2-win-x86.exe /Q
del /F /Q C:\windowsdesktop-runtime-8.0.2-win-x86.exe
cls







**2.Visualcc+DirectX:**


@echo off

rem Set the URL for DirectX installer
set DX_URL=https://download.microsoft.com/download/1/7/1/1718CCC4-6315-4D8E-9543-8E28A4E18C4C/dxwebsetup.exe

rem Set the URL for Visual C++ Redistributable AIO installer
set VC_REDIST_URL=https://github.com/abbodi1406/vcredist/releases/latest/download/VisualCppRedist_AIO_x86_x64.exe

rem Download DirectX installer
echo Downloading DirectX installer...
certutil -urlcache -split -f %DX_URL% dxwebsetup.exe > nul

rem Download Visual C++ Redistributable AIO installer
echo Downloading Visual C++ Redistributable AIO...
certutil -urlcache -split -f %VC_REDIST_URL% VisualCppRedist_AIO_x86_x64.exe > nul

rem Check if files were downloaded successfully
if not exist dxwebsetup.exe (
    echo Error: DirectX installer download failed.
    goto :cleanup
)

if not exist VisualCppRedist_AIO_x86_x64.exe (
    echo Error: Visual C++ Redistributable AIO installer download failed.
    goto :cleanup
)

rem Install DirectX silently
echo Installing DirectX...
dxwebsetup.exe /Q

rem Install Visual C++ Redistributable AIO silently
echo Installing Visual C++ Redistributable AIO...
start /wait VisualCppRedist_AIO_x86_x64.exe /aiA /gm2

echo Installation complete.

:cleanup
rem Delete downloaded files
echo Cleaning up...
del dxwebsetup.exe
del VisualCppRedist_AIO_x86_x64.exe

echo Cleanup complete.
pause

