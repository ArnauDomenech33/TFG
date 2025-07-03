# TFG
**Implementation of Augmented Reality through Unity in the Drone Engineering Ecosystem** 

This project aims to develop an augmented reality application for controlling a drone using 3D waypoints developed with Unity. It is divided into two fundamental parts:
- `Unity Develop Files`: project source files in Unity (editable and expandable).
- `Unity Final App`: final application compiled and ready to run.

## UNITY DEVELOP FILES:
This is the complete editable Unity project. It contains everything necessary to open it with Unity and continue the development of the system. The main structure includes this files:
- `Assets/`: scripts, scenes (Scenes/), prefabs, interfaces, UI, and resources. This is the main file, where all code has been developed.
- `Packages/`: necessary dependencies like TextMeshPro, Input System, etc.
- `ProjectSettings/:` configuration of the project (resolution, execution, tags, layers...).
- `Logs/, UserSettings/`: auxiliary development data.

#### SCRIPTS STRUCTURE AND FUNCTIONALITY
- `CameraScript.cs`: Control the camera in the game scene. Follow the drone from a third person perspective, allowing the user to correctly visualize the environment and navigation.
- `CircuitSelector.cs`: Manages the selection of predefined waypoints circuits. Saves information about which circuit the user has selected and its waypoints.
- `DronPositionSync.cs`: Synchronizes the position of the virtual drone with the telemetry received from the real or simulated drone. It ensures that the position and orientation of the object in Unity reflects reality.
- `DronMAVLinkScript.cs`: Manage the connection and communication with the drone, either in simulation or production mode. It collects data via MAVLink, updates the telemetry and allows the user to connect or disconnect the drone.
- `MenuScript.cs`: Manages navigation between menus and scenes within the application. It includes actions such as going to the main menu, starting the simulation, accessing the waypoint editor or exiting the app.
- `TemporaryWaypointStorage.cs`: Static class to temporarily store waypoints defined by the user and the selected circuit type. The objective of this script is to save the data fi the scene is switched.
- `WaypointManager.cs`: Controls the creation and navigation between manual waypoints. It allows the drone to move towards points defined by the user, manage the orientation (heading) and the altitude of each waypoint.
- `WaypointMenuScript.cs`: User interface script for the waypoint editor. Allows the user to add, delete and modify waypoints.

#### HOW TO CONTINUE DEVELOPING THE PROJECT:
1. Install Unity: recomended same version has de project (6000.0.45f1).
2. Open the project: Open Unity Hub, select "Add project" and select the downloaded Unity Develope Files folder.
3. Scenes: The main scenes are found in Assets/Scenes/. The scenes created in this project are:
  - Menu: Start menu scene. Two option: quit the app or play.
  - WaypointsMenu: Management of waypoints. Here the user can create waypoints or select a circuit and connect to the drone.
  - PlayMenu: Visualization and execution of the augmented reality. Here the camera can be opened and the waypoints spawned.
4. In order to connect to the drone, the user can toggle between:
  - Simulation mode: TCP connection, used with a simulated Drone (Mission Planner).
  - Production mode: Serial port connection, used with a real drone. COM port number where the telemetry receiver is connected must be written.



## UNITY FINAL APP:
The Unity Final APP folder contains the compiled and executable version of the application. You don't need Unity to use it. Includes:
- `Video DronAR.exe`: Main executable file.
- `Video DronAR_Data/`: All the resources needed to run the app.
- `UnityPlayer.dll, .pdb`, and other binary files.
- `MonoBleedingEdge/`: Unity scripting engine.
- `UnityCrashHandler64.exe`: Management of execution errors.
- Standard dependencies of a Unity build for Windows.

### HOW TO EXECUTE THE APP:
1. Double-click DronAR.exe.
2. Main menu screen is sown:
 -  `Play`: Access the waypoint control scene.
 -  `Quit`: closes the application.
3. Waypoint control scene is shown: User can create waypoints manually or select predefined waypoints that create a circuit.
4. Drone connection: after waypoints are defined, select between `Simulation` (simulated drone) or `Production` (real drone) mode and press `Connect`. If `Production mode` is selected, the user must write the `COM` port number where the telemetry receiver is connected.
5. Drone telemetry data will appear.
6. Press `Play` and PlayMenu scene is displayed:
  - Press `Camera On button` to open the camera, if more than one camera is connected, `Switch Camera` button can be pressed to change between cameras.
  - Press `Start`to show the waypoints.


