# Setup Arduino

### 1. Install the Arduino IDE
Arduino IDE is an integrated development environment for Arduino, which is used for single-chip microcomputer software programming, downloading, testing, and more. You can download and install the Arduino IDE for your operating system here:

- [Arduino IDE Download](https://www.arduino.cc/en/Main/Software)

### 2. Install the USB Driver
To connect Arduino to your PC, you'll need the appropriate USB driver, depending on the USB chip your Arduino uses. For many boards like this one, the **CP2102 USB Driver** is required.

- [CP2102 USB Driver Download](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)  
*Note: Be sure to download the driver that corresponds to your operating system.*

Once downloaded and installed, connect your Arduino to the USB port of your PC.

#### For Windows Users:
- Go to **Device Manager**.
- Click **Add Drivers** in the top left pane.
- Navigate to the folder where the driver was downloaded (typically in the Downloads folder after extracting the ZIP file).
- Complete the installation.

### 3. Start the Arduino IDE
Now that everything is connected and installed, you can start using the Arduino IDE.

1. Open the **Arduino IDE** on your PC.
2. Click on **Tools -> Board -> Arduino AVR Boards -> Arduino Uno** to select the correct Development Board Model.
3. Go to **Tools -> Port** and select the appropriate COM port for your board (for example, on Windows, it may show as **COM3**).

Once you've selected the correct board and port, you're ready to start programming with Arduino!

### All Set Now!
You're ready to begin your journey with Arduino Uno. Happy tinkering!

