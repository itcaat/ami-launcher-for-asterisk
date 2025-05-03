# AMI-Launcher for Asterisk

AMI-Launcher is a Windows application that executes external applications or opens web pages in response to Asterisk PBX call events. It connects to the Asterisk Manager Interface (AMI) to monitor call activity and can trigger different applications at various stages of a call.

## Features

- Monitors call activity through Asterisk Manager Interface (AMI)
- Executes applications or opens web pages at different call stages:
  - Before call answer
  - After call answer
  - After call hangup
- Supports passing caller ID information to launched applications
- Notification area icon with status indicators
- Pattern-based phone number matching
- Remote settings configuration via a REST API

## System Requirements

- Windows operating system
- .NET Framework 4.5 or higher
- Asterisk PBX server with AMI enabled

## Configuration

AMI-Launcher requires connection to an Asterisk server with the following parameters:
- AMI Server IP address
- AMI Port (default: 5038)
- AMI Username
- AMI Password

The application can trigger actions at three stages:
1. **Before Answer**: When a call is starting but not yet answered
2. **After Answer**: When a call is connected
3. **After Call**: When a call is disconnected

Each action can be configured with:
- An application path or web URL
- Command-line arguments or URL parameters (supports {callerid} placeholder)

## Building the Project

The solution contains several projects:
- **AsterNET**: Core library for Asterisk AMI communication
- **AsterNET.WinForm**: Main application with GUI
- **AsterNET.Test**: Test project

To build the project:
1. Open `Asterisk.2013.sln` in Visual Studio 2013 or newer
2. Build the solution

## Usage

1. Launch the application
2. Configure the AMI connection settings
3. Set up the applications to be executed at different call stages
4. Define your phone number pattern for call matching
5. Connect to the AMI server

When a call matching your phone pattern is detected, the configured applications will be launched at the appropriate stages.

## License

This project is open source and available under [LICENSE]

## Credits

AMI-Launcher uses the AsterNET library for Asterisk Manager Interface communication.
