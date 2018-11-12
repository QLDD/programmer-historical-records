### 1、!include: could not find: "D:\qp_file\脑图实验版\tm4client\node_modules\app-builder-lib\templates\nsis\include\StdUtils.nsh"


``` js
Error: D:\MyConfiguration\qp29689.TCENT.000\AppData\Local\electron-builder\Cache\nsis\nsis-3.0.3.2\Bin\makensis.exe exited with code 1
Output:
Command line defined: "APP_ID=com.ly.tcentmanager"
Command line defined: "APP_GUID=f4d5dc81-e0b5-52de-9795-cbec8e84429f"
Command line defined: "UNINSTALL_APP_KEY=f4d5dc81-e0b5-52de-9795-cbec8e84429f"
Command line defined: "PRODUCT_NAME=ͬ�̹ܼ�"
Command line defined: "PRODUCT_FILENAME=ͬ�̹ܼ�"
Command line defined: "APP_FILENAME=tm-desktop"
Command line defined: "APP_DESCRIPTION=tm4.0"
Command line defined: "VERSION=4.3.0"
Command line defined: "PROJECT_DIR=D:\qp_file\��ͼʵ���\tm4client"
Command line defined: "BUILD_RESOURCES_DIR=D:\qp_file\��ͼʵ���\tm4client\build"
Command line defined: "MUI_ICON=D:\qp_file\��ͼʵ���\tm4client\build\icons\icon.ico"
Command line defined: "MUI_UNICON=D:\qp_file\��ͼʵ���\tm4client\build\icons\icon.ico"
Command line defined: "APP_32=D:\qp_file\��ͼʵ���\tm4client\build\tm-desktop-4.3.0-ia32.nsis.7z"
Command line defined: "APP_32_NAME=tm-desktop-4.3.0-ia32.nsis.7z"
Command line defined: "APP_32_HASH=A8DDA844BA41EBBE17ADFD599BB22CDF2E368A47784E2FC79C57977C827C7BD10D9217695467A5023AFDE66ACA3AC253B658CFCCAAA4FBE391D46F314E34BF53"
Command line defined: "COMPANY_NAME=Copyright ? 2002-2017 Copyright TongCheng Ltd."
Command line defined: "APP_PRODUCT_FILENAME=ͬ�̹ܼ�"
Command line defined: "APP_INSTALLER_STORE_FILE=ͬ�̹ܼ�\__installer.exe"
Command line defined: "COMPRESSION_METHOD=7z"
Command line defined: "ONE_CLICK"
Command line defined: "RUN_AFTER_FINISH"
Command line defined: "INSTALL_MODE_PER_ALL_USERS"
Command line defined: "INSTALL_MODE_PER_ALL_USERS_REQUIRED"
Command line defined: "SHORTCUT_NAME=ͬ�̹ܼ�"
Command line defined: "UNINSTALL_DISPLAY_NAME=ͬ�̹ܼ� 4.3.0"
Command line defined: "ESTIMATED_SIZE=125647"
Command line defined: "COMPRESS=auto"
Command line defined: "BUILD_UNINSTALLER"
Command line defined: "UNINSTALLER_OUT_FILE=D:\qp_file\��ͼʵ���\tm4client\build\.__uninstaller-nsis-tm-desktop.exe"
Processing config: D:\MyConfiguration\qp29689.TCENT.000\AppData\Local\electron-builder\Cache\nsis\nsis-3.0.3.2\nsisconf.nsh
Processing script file: "<stdin>" (ACP)

Error output:
!include: could not find: "D:\qp_file\脑图实验版\tm4client\node_modules\app-builder-lib\templates\nsis\include\StdUtils.nsh"
Error in script "<stdin>" on line 1 -- aborting creation process

    at ChildProcess.childProcess.once.code (D:\qp_file\脑图实验版\tm4client\node_modules\app-builder-lib\node_modules\builder-util\src\util.ts:254:14)
    at Object.onceWrapper (events.js:317:30)
    at emitTwo (events.js:126:13)
    at ChildProcess.emit (events.js:214:7)
    at maybeClose (internal/child_process.js:925:16)
    at Process.ChildProcess._handle.onexit (internal/child_process.js:209:5)
```

- 原因： 在 electron-builder 打包过程中，路径包含中文，无法识别，换成英文后问题解决。

