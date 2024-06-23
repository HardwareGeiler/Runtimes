@echo off
cls
setlocal enabledelayedexpansion

:: Enable ANSI Escape Sequences
reg add "HKCU\CONSOLE" /v "VirtualTerminalLevel" /t REG_DWORD /d "1" /f

set b=[94m
set c=[36m
set r=[31m
set d=[0m
set m=[95m
set u=[4m

:: Title and Description
:Menu
chcp 65001 >nul 2>&1
cls
echo                                         %c%=====================================
echo                                         %c%=       %b% Framework Installer %d%      %c% =  %d%
echo                                         %c%=====================================
echo                                         %c%=%d%  %b%%u%Select an option to proceed:%d%     %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%  %b%1. Install .NET Frameworks       %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%  %b%2. Install Visual C++            %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%  %b%3. Install DirectX               %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%  %b%4. Install All                   %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%  %b%5. Information %d%                  %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%  %b%6. Exit %d%                         %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%===================================== %d%
echo                                         %c%=  %b%   Created by HardwareGeiler   %c%  =
echo                                         %c%===================================== %d%
echo.
echo                                                %b%Enter your choice (1-6) %b%
set /p choice=
if "%choice%"=="1" goto InstallFrameworks
if "%choice%"=="2" goto InstallVC
if "%choice%"=="3" goto InstallDirectX
if "%choice%"=="4" goto InstallAll
if "%choice%"=="5" goto Information
if "%choice%"=="6" goto Exit

:: Invalid choice
echo Invalid choice. Try again!
pause
goto Menu
exit

:InstallFrameworks
cls
:: Check if .NET Framework 4.8.1 is installed
reg query "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full" /v Version | find "4.8.09032" >nul 2>&1
if %errorlevel% equ 0 (
    echo .NET Framework 4.8.1 is already installed.
) else (
    echo Installing .NET Framework 4.8.1...
    powershell -Command "Invoke-WebRequest 'https://download.microsoft.com/download/4/b/2/cd00d4ed-ebdd-49ee-8a33-eabc3d1030e3/NDP481-x86-x64-AllOS-ENU.exe' -OutFile '%temp%\NDP481-x86-x64-AllOS-ENU.exe'"
    start /wait %temp%\NDP481-x86-x64-AllOS-ENU.exe /Q
    del /F /Q %temp%\NDP481-x86-x64-AllOS-ENU.exe
)


:: Check if .NET 5.0 is installed
dotnet --list-runtimes | find "Microsoft.NETCore.App 5.0." >nul
if %errorlevel% equ 0 (
    echo .NET 5.0 is already installed.
) else (
    echo Installing .NET 5.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/b6fe5f2a-95f4-46f1-9824-f5994f10bc69/db5ec9b47ec877b5276f83a185fdb6a0/windowsdesktop-runtime-5.0.17-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-5.0.17-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-5.0.17-win-x86.exe /Q
    del /F /Q %temp%\windowsdesktop-runtime-5.0.17-win-x86.exe
)

:: Check if .NET 6.0 is installed
dotnet --list-runtimes | find "Microsoft.NETCore.App 6.0." >nul
if %errorlevel% equ 0 (
    echo .NET 6.0 is already installed.
) else (
    echo Installing .NET 6.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/a9669480-f3e0-42a6-b381-108950dfe290/b54d6613c0fa2839c41d61478926ccb9/windowsdesktop-runtime-6.0.27-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-6.0.27-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-6.0.27-win-x86.exe /Q
    del /F /Q %temp%\windowsdesktop-runtime-6.0.27-win-x86.exe
)

:: Check if .NET 7.0 is installed
dotnet --list-runtimes | find "Microsoft.NETCore.App 7.0." >nul
if %errorlevel% equ 0 (
    echo .NET 7.0 is already installed.
) else (
    echo Installing .NET 7.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/ff4b13ba-07aa-4aa7-b5ae-9111c363c802/5fdedee9a9fae645bfdda3a8930c923d/windowsdesktop-runtime-7.0.16-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-7.0.16-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-7.0.16-win-x86.exe /Q
    del /F /Q %temp%\windowsdesktop-runtime-7.0.16-win-x86.exe
)

:: Check if .NET 8.0 is installed
dotnet --list-runtimes | find "Microsoft.NETCore.App 8.0." >nul
if %errorlevel% equ 0 (
    echo .NET 8.0 is already installed.
	pause
) else (
    echo Installing .NET 8.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/9b77b480-7e32-4321-b417-a41e0f8ea952/3922bbf5538277b1d41e9b49ee443673/windowsdesktop-runtime-8.0.2-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-8.0.2-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-8.0.2-win-x86.exe /Q
    del /F /Q %temp%\windowsdesktop-runtime-8.0.2-win-x86.exe
)

echo .NET Frameworks and .NET versions installed successfully.
goto Menu

:InstallVC
cls
reg query HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Uninstall /s /f "Microsoft Visual C++" > nul 2>&1
if %errorlevel% == 0 (
    echo Visual C++ Redistributable is already installed.
) else (
    echo Installing Visual C++ Redistributable...
    powershell -Command "Invoke-WebRequest 'https://kutt.it/vcpp' -OutFile '%temp%\vc_redist.x64.exe'"
    start /wait %temp%\vc_redist.x64.exe /ai /gm2
)
echo Visual C++ Redistributable installed successfully.
pause
goto Menu

:InstallDirectX
cls
:: Check if DirectX is installed
if exist "%windir%\System32\dxdiag.exe" (
    echo DirectX is already installed.
) else (
    echo Installing DirectX...
    powershell -Command "Invoke-WebRequest 'https://download.microsoft.com/download/1/7/1/1718CCC4-6315-4D8E-9543-8E28A4E18C4C/dxwebsetup.exe' -OutFile '%temp%\dxwebsetup.exe'"
    start /wait %temp%\dxwebsetup.exe /silent
)
echo DirectX installed successfully.
pause
goto Menu

:InstallAll
cls
echo Installing all components...
call :InstallFrameworks
call :InstallVC
call :InstallDirectX
echo All components installed successfully.
goto Menu

:Information
cls
echo                                         %c%=====================================%d%
echo                                        %c% = %d%       %b% Information  Menu        %c% =%d%
echo                                         %c%=====================================%d%
echo                                         %c%=%d%  %u%%b%Select an option to learn more:%d%  %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%%b%  1. About NET Framework           %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%%b%  2. About Visual C++              %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%%b%  3. About DirectX                 %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=%d%%b%  4. Back to Main Menu             %c%=%d%
echo                                         %c%=                                   =  %d%
echo                                         %c%=====================================%d%
echo.
echo                                                 %b%Enter your choice (1-4)
set /p infochoice=

if "%infochoice%"=="1" goto InfoDotNet
if "%infochoice%"=="2" goto InfoVC
if "%infochoice%"=="3" goto InfoDirectX
if "%infochoice%"=="4" goto Menu

:: Invalid choice
echo Invalid choice. Please run the script again.
pause
goto Information

:InfoDotNet
cls
echo .NET Framework is a software framework developed by Microsoft that runs primarily on Microsoft Windows.
echo It includes a large class library called Framework Class Library (FCL) and provides language interoperability
echo across several programming languages. Programs written for .NET Framework execute in a software environment
echo named the Common Language Runtime (CLR). To learn more, visit:
echo https://learn.microsoft.com/en-us/dotnet/framework/get-started/overview
pause
goto Information

:InfoVC
cls
echo Visual C++ Redistributable is a package of Microsoft C++ (MSVC) runtime libraries.
echo These libraries are required to run applications developed with Visual Studio on a computer
echo that does not have Visual Studio installed. To learn more, visit:
echo https://docs.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist
pause
goto Information

:InfoDirectX
cls
echo DirectX is a collection of application programming interfaces (APIs) for handling tasks related to multimedia,
echo especially game programming and video, on Microsoft platforms. It is essential for games and high-performance
echo multimedia applications. To learn more, visit:
echo https://www.microsoft.com/en-us/download/details.aspx?id=35
pause
goto Information

:Main
cls
echo Returning to main menu...
goto Menu

:AlrInstalled
cls
echo This is already installed.
pause
goto Menu

:End
echo =======================================
echo Installation process completed.
pause
exit

:Exit
exit
