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

    echo Installing .NET 5.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/3789ec90-2717-424f-8b9c-3adbbcea6c16/2085cc5ff077b8789ff938015392e406/aspnetcore-runtime-5.0.17-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-5.0.17-win-x64.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/4bfa247d-321d-4b29-a34b-62320849059b/8df7a17d9aad4044efe9b5b1c423e82c/aspnetcore-runtime-5.0.17-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-5.0.17-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-5.0.17-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-5.0.17-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-5.0.17-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-5.0.17-win-x64.exe

    echo Installing .NET 6.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/f6b6c5dc-e02d-4738-9559-296e938dabcb/b66d365729359df8e8ea131197715076/windowsdesktop-runtime-6.0.36-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-6.0.36-win-x64.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/cdc314df-4a4c-4709-868d-b974f336f77f/acd5ab7637e456c8a3aa667661324f6d/windowsdesktop-runtime-6.0.36-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-6.0.36-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-6.0.36-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-6.0.36-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-6.0.36-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-6.0.36-win-x64.exe

    echo Installing .NET 7.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/08bbfe8f-812d-479f-803b-23ea0bffce47/c320e4b037f3e92ab7ea92c3d7ea3ca1/windowsdesktop-runtime-7.0.20-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-7.0.20-win-x64.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/b840017b-c69f-4724-a152-11020a0039e6/b74aa12e4ee765a3387a7dcd4ba56187/windowsdesktop-runtime-7.0.20-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-7.0.20-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-7.0.20-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-7.0.20-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-7.0.20-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-7.0.20-win-x64.exe

    echo Installing .NET 8.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/27bcdd70-ce64-4049-ba24-2b14f9267729/d4a435e55182ce5424a7204c2cf2b3ea/windowsdesktop-runtime-8.0.11-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-8.0.11-win-x86.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/6e1f5faf-ee7d-4db0-9111-9e270a458342/4cdcd1af2d6914134308630f048fbdfc/windowsdesktop-runtime-8.0.11-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-8.0.11-win-x64.exe'"
    start /wait %temp%\windowsdesktop-runtime-8.0.11-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-8.0.11-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-8.0.11-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-8.0.11-win-x64.exe

	echo Installing .NET 9.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/685792b6-4827-4dca-a971-bce5d7905170/1bf61b02151bc56e763dc711e45f0e1e/windowsdesktop-runtime-9.0.0-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-9.0.0-win-x86.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/8dfbde7b-c316-418d-934a-d3246253f342/69c6a35b77a4f01b95588e1df2bddf9a/windowsdesktop-runtime-9.0.0-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-9.0.0-win-x64.exe'"
    start /wait %temp%\windowsdesktop-runtime-9.0.0-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-9.0.0-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-9.0.0-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-9.0.0-win-x64.exe
	
goto Menu

:InstallVC
cls

    echo Installing Visual C++ Redistributable...
    powershell -Command "Invoke-WebRequest 'https://kutt.it/vcpp' -OutFile '%temp%\vc_redist.x64.exe'"
    start /wait %temp%\vc_redist.x64.exe /aiA /gm2

echo Visual C++ Redistributable installed successfully.
pause
goto Menu

:InstallDirectX
cls
echo Installing DirectX...
powershell -Command "Invoke-WebRequest 'https://download.microsoft.com/download/1/7/1/1718CCC4-6315-4D8E-9543-8E28A4E18C4C/dxwebsetup.exe' -OutFile '%temp%\dxwebsetup.exe'"
start /wait %temp%\dxwebsetup.exe /Q
echo DirectX installed successfully.
pause
goto Menu

:InstallAll
cls
echo Installing all components...
echo InstallFrameworks

    echo Installing .NET 5.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/3789ec90-2717-424f-8b9c-3adbbcea6c16/2085cc5ff077b8789ff938015392e406/aspnetcore-runtime-5.0.17-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-5.0.17-win-x64.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/4bfa247d-321d-4b29-a34b-62320849059b/8df7a17d9aad4044efe9b5b1c423e82c/aspnetcore-runtime-5.0.17-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-5.0.17-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-5.0.17-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-5.0.17-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-5.0.17-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-5.0.17-win-x64.exe

    echo Installing .NET 6.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/f6b6c5dc-e02d-4738-9559-296e938dabcb/b66d365729359df8e8ea131197715076/windowsdesktop-runtime-6.0.36-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-6.0.36-win-x64.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/cdc314df-4a4c-4709-868d-b974f336f77f/acd5ab7637e456c8a3aa667661324f6d/windowsdesktop-runtime-6.0.36-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-6.0.36-win-x86.exe'"
    start /wait %temp%\windowsdesktop-runtime-6.0.36-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-6.0.36-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-6.0.36-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-6.0.36-win-x64.exe

    echo Installing .NET 7.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/08bbfe8f-812d-479f-803b-23ea0bffce47/c320e4b037f3e92ab7ea92c3d7ea3ca1/windowsdesktop-runtime-7.0.20-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-7.0.20-win-x64.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/b840017b-c69f-4724-a152-11020a0039e6/b74aa12e4ee765a3387a7dcd4ba56187/windowsdesktop-runtime-7.0.20-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-7.0.20-win-x64.exe'"
    start /wait %temp%\windowsdesktop-runtime-7.0.20-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-7.0.20-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-7.0.20-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-7.0.20-win-x64.exe

    echo Installing .NET 8.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/27bcdd70-ce64-4049-ba24-2b14f9267729/d4a435e55182ce5424a7204c2cf2b3ea/windowsdesktop-runtime-8.0.11-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-8.0.11-win-x86.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/6e1f5faf-ee7d-4db0-9111-9e270a458342/4cdcd1af2d6914134308630f048fbdfc/windowsdesktop-runtime-8.0.11-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-8.0.11-win-x64.exe'"
    start /wait %temp%\windowsdesktop-runtime-8.0.11-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-8.0.11-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-8.0.11-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-8.0.11-win-x64.exe

	echo Installing .NET 9.0...
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/685792b6-4827-4dca-a971-bce5d7905170/1bf61b02151bc56e763dc711e45f0e1e/windowsdesktop-runtime-9.0.0-win-x64.exe' -OutFile '%temp%\windowsdesktop-runtime-9.0.0-win-x86.exe'"
    powershell -Command "Invoke-WebRequest 'https://download.visualstudio.microsoft.com/download/pr/8dfbde7b-c316-418d-934a-d3246253f342/69c6a35b77a4f01b95588e1df2bddf9a/windowsdesktop-runtime-9.0.0-win-x86.exe' -OutFile '%temp%\windowsdesktop-runtime-9.0.0-win-x64.exe'"
    start /wait %temp%\windowsdesktop-runtime-9.0.0-win-x86.exe /q
    start /wait %temp%\windowsdesktop-runtime-9.0.0-win-x64.exe /q
    del /F /Q %temp%\windowsdesktop-runtime-9.0.0-win-x86.exe
    del /F /Q %temp%\windowsdesktop-runtime-9.0.0-win-x64.exe

echo InstallVC

  echo Installing Visual C++ Redistributable...
    powershell -Command "Invoke-WebRequest 'https://kutt.it/vcpp' -OutFile '%temp%\vc_redist.x64.exe'"
    start /wait %temp%\vc_redist.x64.exe /aiA /gm2

echo InstallDirectX

echo Installing DirectX...
powershell -Command "Invoke-WebRequest 'https://download.microsoft.com/download/1/7/1/1718CCC4-6315-4D8E-9543-8E28A4E18C4C/dxwebsetup.exe' -OutFile '%temp%\dxwebsetup.exe'"
start /wait %temp%\dxwebsetup.exe /Q

pause
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

:Exit
exit
