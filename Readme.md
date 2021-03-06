Example project on how to setup a STM32 Microcontroller with USB port to run the BleuIO dongle with the STM32 as a USB CDC Host and control LCD display connected to it.

# 1. What you will need

- Two BleuIO dongle (https://www.bleuio.com/)
- A board with a STM32 Microcontroller with a USB port. (A Nucleo-144 development board: NUCLEO-H743ZI2, was used developing this example. (https://www.st.com/en/evaluation-tools/nucleo-h743zi.html)<br>
  To connect the dongle to the Nucleo board we used a "USB A to Micro USB B"-cable with a USB A female-to-female adapter.)
- STM32CubeIDE (https://www.st.com/en/development-tools/stm32cubeide.html)
- Liquid Crystal Display Module – NHD-0420D3Z-NSW-BBW-V3 (https://www.newhavendisplay.com/nhd0420d3znswbbwv3-p-5745.html)
- HibouAir - Air quality monitoring device (https://www.hibouair.com/)

# 2. How to setup project

## 2.1 Downloading the project from GitHub

Either clone the project, or download it as a zip file and unzip it, into your STM32CubeIDE workspace.

## 2.2 Importing as an Existing Project

- From STM32CubeIDE choose File>Import...>General>Existing Projects into Workspace then click 'Next >'
- Make sure you've choosen your workspace in 'Select root directory:'
- You should see the project "stm32_bleuio_example", check it and click 'Finish'.

# 3. Running the example

- In STMCubeIDE click the hammer icon to build the project.
- Open up the 'STMicroelectronics STLink Viritual COM Port' with a serial terminal emulation program like TeraTerm, Putty or CoolTerm.

  > Baudrate: 115200

  > Data Bits: 8

  > Parity: None

  > Stop Bits: 1

  > Flow Control: None

- In STMCubeIDE click the green play button to flash and run it on your board. The first time you click it the 'Run Configuration' window will appear. You can just leave it as is and click run.

- Connect the BleuIO Dongle.
- Wait until the message: "[BleuIO Dongle Ready]" is shown.
- Press 0 to get device information, 1 to start advertising and 2 to stop advertising. Dongle response will be printed to uart.
# 4. Web script
- Open script.js from web script folder in the root directory.
- Update the BleuIO dongles device id (dongleToConnect) on line 4 that is connected to STM32 board.
- Run the script using a web bundler (parcel js) by typing parcel index.html

