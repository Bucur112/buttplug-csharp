# 0.3.3 (2019-01-13)

## Features

- Added Hardware Support
  - Vorze Bach
- Moved TestServer/DeviceManager/Device to Core library for examples
- Updated dependencies

# 0.3.2 (2018-11-23)

## Features

- Added Hardware Support
  - Picobong Toys (All)
  
## Bugfixes

- Updates schema to fix LinearCmd issue

# 0.3.1 (2018-11-08)

## Features

- Added Hardware Support
  - Lovense Osci
  - Magic Motion Magic Wand
  - Magic Motion Magic Kegel Twins
  
## Bugfixes

- Updated schema to fix NJsonSchema parsing issues
- Fixed issue with not being able to scan for devices more than once per session

# 0.3.0 (2018-11-03)

## Features

- Added Hardware Support
  - Kiiroo Titan
  - Kiiroo Onyx 1 (Bluetooth)
  - WeVibe Classic
- Made code more C#-y
  - Methods exposed to developers now throws exceptions on errors, versus returning Buttplug Messages
  - All async methods now end in Async, take cancellation tokens
- Complete rewrite of Client API
  - More closely resembles buttplug-js client API
  - Uses extensible Connector setup for managing communications
  - More ergonomic API for developers, should never have to form raw Buttplug Messages
  - Server now searches local DLLs for Subtype Managers, versus requiring client to specifically add them
- Nuget Core/Client/Server packages now condensed to Buttplug package
- Buttplug package and Client/Server connectors now .Net Standard/Framework, supporting on Linux/Mac as well as Windows
  - Hardware Subtype Manager libraries still .Net Framework, because they're windows specific
- Lovense devices now support LovenseCmd message
- IPC Connectors for Client/Server
- SerialPortManager now capable of using protocols other than ET312
- Remove GUI applications (now at https://github.com/buttplugio/buttplug-windows-suite)
- Kiiroo Emulator completely removed
- Added example/tutorial programs to show developers how Buttplug C# should work
- Lots of Documentation updates
- Added Copyright to (most) files
- Lots more tests
- Converted all tests to using FluentAssertions
- Print Bluetooth radio info on first scan when logging at Debug or higher
- Use Types over strings where possible

## Bugfixes

- Lovense legacy devices (using BLE Indicate) now detected via same method as newer devices
- Catch exception when serial port with incorrect name shows up
- Lots of Resharper warnings fixes
- Lots of spelling fixes

# 0.2.3 (2018-05-23)

## Bugfixes

- Fix issue with Launch not connecting
- Fix issue with WeVibe/Youcups devices not being found

# 0.2.2 (2018-05-21)

## Features

- Added Hardware Support
  - Vorze UFO SA
  - LiBo Whale
  - MysteryVibe Crescendo
  - Cyclone X10 (USB)
  - Kiiroo Onyx 2
- Added name prefix device searching (Hopefully fixes Lovense update problems)
- Rename WebsocketServer to Server in preparation for IPC
- Add signal multiplier to GVR, for games with light vibration
- Add controller passthru to GVR, to allow turning off gamepad rumble when routing to toys

## Bugfixes

- Remove ping checking from Server to stop background tab disconnects
  on webbrowsers
- Move all .Net Standard project to .Net 4.7
- Update dependencies
- Change server GUI from disappearing to disabling on server stop
- Clear last error on server on successful connect or server start
- Fix lockup when closing applications that use the device tab and have a device scan going
- Fix crash when device names is missing in friendly name tables
- Fix crash when trying to open link on systems without a browser selected.
- Fix crash when Crypto key can't be written to disk
- Fix crash when Trancevibrator registry lookup returns unexpected types

# 0.2.1 (2018-03-08)

## Features

- Added Hardware Support
  - Lovense Lush/Domi/Edge (new firmware versions)
  - WeVibe Sync
  - Kiiroo Pearl 2
  - Pornhub Blowbot
  - Rez Trancevibrator (Win 7 only)
- Game Vibration Router now have "Vibes" tab to show incoming vibration commands
- Added individual vibrator control for WeVibes

## Bugfixes

- Fixed XInput DLL missing crash
- Fixed BAD DATA error/crash on accepting certs
- Moved all Non .Net Standard projects to .Net 4.7
- Far more test coverage
- Game Vibration Router only updates toys at 20hz max

# 0.2.0 (2018-01-22)

## Features

- Added Hardware Support
  - Youcups Warrior II Masturbator
  - Erostek ET312B
  - Wevibe 4
  - OhMiBod/Kiiroo Fuse
  - Lovense Edge/Hush/Domi (new firmware versions)
  - Individual Vibrator support for Lovense Edge
- Now uses v1 of the Buttplug Protocol spec, adds new generic messages, as well as feature counts for device messages
- Supports message downgrading, meaning older clients can connect to newer servers
  - Newer clients cannot connect to older servers, though
- Moved code to .Net Standard 2.0 compatibility
- Moved testing to NUnit

## Bugfixes

- Game Router process select button disabled until process selected
- Fix SynchronizationContext crash in client

# 0.1.3 (2017-12-07)

## Features

- Add ignore cert errors for client library
- Handle message ID iteration in client library

# 0.1.2 (2017-09-15)

## Bugfixes

- Fix ArgumentOutOfBoundsException in updater

# 0.1.1 (2017-09-15)

## Features

- Added auto update and update checking functionality
- Added support for the following hardware
  - WeVibe 4 Plus, Ditto, Nova, Pivot, Wish, Verge
  - Lovense Domi
- Added more product names for the Lovense Hush (LVS-Z36, LVS_Z001)
- Added Game Vibration Router application
- WebsocketServer now defaults to SSL

## Bugfixes

- Fixed hang when no XBox controllers and no Bluetooth adapters are
  connected
- SSL Errors in Websocket Server are now shown in GUI or as a
  notification, not in modal dialogs
- Fixed ObjectDisposed Exception in Kiiroo App
- Fixed port number changing in Websocket Server
- Fixed crash when copying IP addresses in Websocket Server
- Fixed version number listing in logs
- Vibratissimo devices now required to be named "Vibratissimo"

# 0.1.0 (2017-08-07)

## Features

- First release
- Added support for the following hardware
  - XInput (XBox) Gamepads
  - Lovense Max, Nora, Lush, Hush, Ambi, Edge (vibration only)
  - Fleshlight Launch
  - Vorze A10 Cyclone
  - Magic Motion toys
  - Vibratissimo toys
- Added libraries (available as nuget packages)
  - Core
  - Client
  - Server
  - XInputGamepadManager
  - UWPBluetoothManager
- Added applications
  - Websocket Server
  - Kiiroo Platform Emulator

# 0.0.0 (2017-04-24)

- Project Started
