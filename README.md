<h1>ADDI AI Coding </h1>
<hr/>
Block coding application utilizing ADDI blocks
<br/><br/>
<h1> 📱 Project Introduction </h1>
<hr/>
Connect Addi blocks via Bluetooth. <br/>
Then, perform block coding and execute it to see the ADDI blocks operate in real-time.
<br/><br/>
<h1>:calendar: When? </h1>
<hr/>
240201~ , KIST_Creamo
<br/><br/>
<h1>🙂 Members </h1>
<hr/>

|Members|
|------|
|[Seungyeon JI](https://github.com/jisally)|
|[Heeyun HEO](https://github.com/Heeyun0724)|
|[Jiwoo BYUN](https://github.com/dede0827)|

<h1>:gear: Environment Setting</h1>
<hr/>

[![예제](http://img.youtube.com/vi/usE9IKaogDU/0.jpg)](https://youtu.be/usE9IKaogDU?t=0s)

<ul>
  <li><b>IDE: Android Studio 2022.3.1.21</b></li>
  <li><b>Flutter SDK: 3.16.8</b></li>
</ul>
<br/><br/>
<h1>▶ How to RUN? </h1>
<hr/>

    flutter run lib/main.dart


<br/>
<h1>🏆 Results </h1>
<hr/>

<h2> MAIN PAGE</h2>

![1](https://github.com/multi-sensor/CREAMO_Team_A/assets/83489449/d09c1b2c-32e4-495d-96c2-a585e66614e2)
<br/>
<h2> START PAGE </h2>

![2](https://github.com/multi-sensor/CREAMO_Team_A/assets/90318181/e7abe5fd-a531-423b-9b7d-d7d2cf21bd78)
<br/>
<h2>CONTENT PAGE</h2>

![image](https://github.com/multi-sensor/CREAMO_Team_A/assets/83489449/d666c85f-9055-41e9-aacb-c7045a1ca730)


<br/>
<h2>HINT PAGE</h2>

![3](https://github.com/multi-sensor/CREAMO_Team_A/assets/83489449/675c4f8f-ce35-4123-86bd-cf90fe6bb71d )

<br/>
<h2>PUZZLE PAGE</h2>

![3](https://github.com/multi-sensor/CREAMO_Team_A/assets/90318181/a033b2ec-726b-4f74-8a86-be7c1fac25b4)

<br/>
** Connection Block**
<br/>
When the user drags and drops Connection Block 1, Connection Block 2 is automatically created below it. Even if these two blocks appear separate on the screen, the server recognizes them as connected.<br/><br/>

** Repeat Block**
<br/>
The blocks following the Repeat Block are repeated on the server according to the number specified in the Repeat Count Block located at the end of the loop.
<br/><br/>
** Speaker Block**
<br/>
When the user executes the Speaker Block and the Speaker On Block, sound is produced from the actual block.
<br/><br/>
** Motor Block**
<br/>
When the user executes the Motor Block and the Direction Block, the actual block moves.
<br/><br/>
** Led Block**
<br/>
When the user executes the LED Block and the Color Block, the actual block lights up.
<br/><br/>
** Image Block**
<br/>
When the user executes the Image Block, a specific shape appears on the actual block.


<h1> 📑Flow Chart </h1>
<hr/>

![002](https://github.com/multi-sensor/CREAMO_Team_A/assets/90318181/62794b7c-946d-42a5-ab11-7297e9e62515)


<br/><br/>
<h1> ➕ Details </h1>
<hr/>

`main.dart`

* The file that runs the application.


`splash_page.dart`

* This is the initial screen where Addi AI coding is executed.


`start_page.dart`

* The page is for choosing between "Getting Started" and "How to Use."


`content_page.dart`

* You can check the quiz table of contents and select a quiz from here.


`puzzle_page.dart`
1. Initialization
- The widget initializes with a given image path for the puzzle.

2. Scrolling Interface
- It provides a horizontally scrollable interface divided into sections. The user can scroll through different sections using buttons.

3. Image Drag and Drop
- Users can drag and drop images onto a target area. The dropped images can snap to specific positions based on predefined snap points.

4. Reset Functionality
- There's a reset button to clear all dropped images and reset the puzzle.

5. Bluetooth Integration
- It includes a button to trigger a Bluetooth scan, and another button to initiate a puzzle-solving process which involves generating a sequence of connected block numbers.

6. Trash Can Feature
- Users can drag images to a trash can area to delete them from the puzzle.

7. Image Snap and Connect
- Images can snap to each other when placed close enough, forming connections. This functionality is crucial for solving the puzzle.

8. Bluetooth Data Transmission
- Upon solving the puzzle, the connected block numbers are formatted and sent via Bluetooth.


`bluetooth_helper.dart`

1. Bluetooth Device Management
- connectedDevice: Represents the currently connected Bluetooth device.
- devices: A list to store available Bluetooth devices discovered during scanning.

2. Bluetooth Scanning
- startBluetoothScan(BuildContext context): Initiates the Bluetooth scan process and handles device discovery.
- _startInitialScanAndShowDevicesDialog(BuildContext context): Starts the initial Bluetooth scan and displays a dialog showing scanning progress.
- _showDevicesDialog(BuildContext context): Shows a dialog with a list of discovered Bluetooth devices, allowing the user to connect to a selected device.

3. Device Connection
- _disconnectDevice(BuildContext context): Disconnects the currently connected device.
- sendData(String data): Sends data to the connected Bluetooth device.

4. Dialogs and Feedback
- _showConnectedDeviceDialog(BuildContext context): Displays information about the currently connected device.
- Feedback through toast messages: Provides feedback to the user regarding connection status and operations (success or failure) using Fluttertoast.

5. Permission Handling
- Requests and handles location permission to enable Bluetooth scanning.

6. Event Handling
- Subscribes to Bluetooth scan results and stops scanning after a specified timeout.
- Handles user interactions such as selecting a device to connect to.

7. Service Discovery and Data Transmission
- Discovers services and characteristics of the connected Bluetooth device.
- Writes data to a writable characteristic of the connected device for data transmission.
