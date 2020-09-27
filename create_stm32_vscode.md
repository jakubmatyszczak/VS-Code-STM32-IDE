# Creating STM32 Project with VS Code
## Requirements

```
sudo apt-get update && sudo apt-get upgrade
sudo apt-get install build-essential arm-none-eabi-gcc openocd
sudo apt-get install python3 python3-pip python3-venv
```

## Setting up the project
1. Create project in CubeMX
2. Select 'Makefile' as Toolchain in Project Manager in CubeMX
3. Open directory in VS Code
4. Ctrl+Shit+P -> 'Workspaces: Save Workspace as...' and create .code-worskpace file in the same directory as CubeMX project
5. Copy ideScripts folder to project directory
6. Copy stlink.cfg, STM_FAMILY.cfg and STM_FAMILY.svd where STM_FAMILIY corresponds to selected chip eg. 'stm32g4x.cfg' and 'stm32g474RE.svd' to main project directory

Directory should now look like this:
```
~/Projects/
	PROJ_NAME/
		PROJ_NAME.ioc
		PROJ_NAME.code-workspace
		ideScripts/
		stlink.cfg
		STM_FAMILY.cfg
		STM_FAMILY.svd
		...
```

7. From integrated Terminal, run the following command, and follow the instructions. When prompted with path specification, use absoute paths to files (right click on file in vscode workspace and click 'Copy Path')
```
python3 ideScripts/update.py
```
8. Project should now be configured and ready to be build, flashed and debugged. Refer