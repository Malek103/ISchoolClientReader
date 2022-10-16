
# Ischool Dahua Client

This project will be installed on a local computer that connected to a Dahua NVR.

## How it works:
The app will do the following:

1. When it start, it will connect to the Dahua NVR and start listening on the events fired by dahua such as when a face detected.
2. The app will periodically fetch the school and camera's setting from ischool website (Backend).
3. It will periodically send the collected data (faces & students) to the Backend.
4. It will update the Dahua faces database when a new student face added in the Backend.



## Technical:
1. This app built using .net 6 
2. The UI is build using [Avalonia UI](https://avaloniaui.net/).
3. SQLite3 is used to cache data locally.
4. It uses [Dahua SDK for C#](https://www.dahuasecurity.com/support/downloadCenter/softwares?id=2&child=3).

## Creating the Setup file
In this project we used [Clowd.Squirrel](https://github.com/clowd/Clowd.Squirrel) packege to manage the releas and update the app.
Each time we create a new release, the package will handle the update process automatically.
#### Required tools:
1. you need to install `csq` tool using the command: `dotnet tool install -g csq`

#### Create the Setup file:
1. publish the dotnet projcet: 
`dotnet publish ISchoolClientReader.csproj --sc -r win-x64 -o ./publish`

2. create the setup file (you need to update the version `-v 1.0.2` ): 
`csq pack -u ischoolClient -v 1.0.2 -p ./publish -e ISchoolClientReader.exe`







