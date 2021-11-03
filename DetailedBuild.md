## Building the Armor GUI Wallet for Windows from source code

To build the gui wallet you must have built **armor core**, so please do all steps from [here](https://github.com/Armor-Network/armor#building-on-windows) before proceeding!

The gui wallet is built with QtCreator. [Qt](https://www.qt.io/) is a toolkit for creating graphical user interfaces as well as cross-platform applications that run on various software and hardware platforms.

[Register for a Qt account](https://login.qt.io/register) to enable downloads.

[Download QTCreator](https://www.qt.io/download-thank-you?os=windows) and run the installer.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/55367064/139972096-ef25cdfd-7525-4289-8b5d-8f988157c081.png)

Enter your login details:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/55367064/139973303-235e211c-f79d-4ef3-ac98-d6aee6f38687.png)

Accept the (Open Source) licence terms.

Choose `Custom installation`:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/55367064/139974644-dc80f0da-d12e-4f53-b5c9-8a179d506a5a.png)

Expand the `Qt` drop-down and select `Qt 5.9.9`:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/55367064/139975495-b2fc491c-7a45-40d6-9b72-9891c9ebab07.png)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;11.5Gb download!

Accept the CMake licence terms then click on `Install`.
The downloads and installation could take some time.


## Clone the armor gui wallet source code:

[Install Git](https://github.com/git-for-windows/git/releases/download/v2.33.1.windows.1/Git-2.33.1-64-bit.exe) if you have not already done so.

When you built **armor core** you created an `armor` directory. Open a command prompt and change to the `armor` directory:

	c:\> cd armor

Clone the armor-gui source code:

	c:\armor> git clone https://github.com/Armor-Network/armor-gui.git
  

## Build armor-gui

From the Windows Start Menu run `QtCreator (Community)`

In the File menu open the armor-gui project file `armor\armor-gui\src\armor-gui.pro`
then select the `Desktop Qt 5.9.9 MSVC 2017 64bit` kit and click `Configure Project`

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/55367064/139990290-6ebf4cb4-fc9f-44ff-8811-b1569699e8f7.png)

In the left sidebar select: ![image](https://user-images.githubusercontent.com/55367064/139995434-a9a6236a-f704-47bb-90e4-720efc101a76.png)

and change it to `Release`: ![image](https://user-images.githubusercontent.com/55367064/139996908-937a5cca-3831-4bd4-83f7-fdec6bcbe2c2.png)

In the left sidebar select `Projects` and check the details:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/55367064/139998617-2610ca3a-506b-437d-9379-b172fa987fb4.png)

On the bottom toolbar select `Compile Output`

In the left sidebar select ![image](https://user-images.githubusercontent.com/55367064/139999222-5ce64601-3a58-40df-8269-273acd60ed7b.png) to start building armor-gui.

Check progress in the `Compile Output` window. The build should run to completion without errors.

You should now have the following assets in the `armor\armor-gui\bin` folder:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;![image](https://user-images.githubusercontent.com/55367064/140000379-15c0488a-74da-4cb4-b9b6-d88c6b5d1d17.png)

(note: `armord.exe`, `armord.pdb`, `walletd.exe` and `walletd.pdb` are copied from the assets created by the armor core build by the armor-gui project file. The *.pdb files are not required to run the armor-gui app)

## Deployment

QT includes a windows deployment tool `windeployqt` which automates the process of creating a deployable folder containing the Qt-related dependencies (libraries, QML imports, plugins, and translations) required to run the application.
<br/>Add the `bin` directory of your Qt installation (e.g. <QT_DIR\bin>) to the PATH variable and then run:  `windeployqt <path-to-app-binary>`, as follows:
<br/><br/>From a Windows command prompt with Administrator privileges (assuming you installed Qt to the default location `c:\Qt`):
	
	setx /M PATH "%PATH%;c:\Qt\5.9.9\msvc2017_64\bin"

To check the PATH:

	echo %PATH%

Close and restart the command prompt, then:

	windeployqt c:\armor\armor-gui\bin

The `\armor\armor-gui\bin` directory should now contain the following assets:

![image](https://user-images.githubusercontent.com/55367064/140002067-e792c7e2-1f3e-4e3a-9f76-7c678cce7283.png)

Create a shortcut to `armor-gui.exe` and run it.
	
If you get error messages that `MSVCP140.dll` and `VCRUNTIME140.dll` were not found, install [Microsoft Visual C++ Redistributable for Visual Studio 2017](https://go.microsoft.com/fwlink/?LinkId=746572)
