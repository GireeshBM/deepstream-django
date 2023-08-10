# DeepStream Django Real-Time Object Detection System with Web Interface

This project combines various sources to create a real-time object detection system based on the web. The system utilizes Python 3.6+, DeepStream 5.1, and Django 2.0 to achieve object detection tasks for counting pedestrian and vehicle flows. The implemented features include:

1. Counting and statistics based on time periods.
2. Data visualization display.
3. Real-time display of monitoring images, screenshot capture, and platform display.
4. Data download functionality.
5. Device status viewing.
6. User authentication and permissions management.

## Design Approach
The project adopts edge deployment using Jetson devices. Each edge device serves as a node for data collection and monitoring processing, as shown in the following diagram:
![Image](https://user-images.githubusercontent.com/40747806/135811095-ab259816-7da2-49ea-b38f-843762691041.png)

## How to Use
### 1. Installation
1. For the backend, install the required packages using the `requirements.txt` file by executing `pip install -r ./requirements.txt`. If the internet connection is slow, you can add a local source for downloading, for example: `pip install -r ./requirements.txt -i https://mirrors.aliyun.com/pypi/simple`

2. For the edge devices, download DeepStream version 5.0 or higher (since this project is developed using Python 3.6, ensure that DeepStream is upgraded to version 5.0 or above, and make sure it's compatible with your JetPack version).

3. The author has provided a one-click startup script on the Jetson device desktop. After obtaining the source code for the Jetson device, you can double-click to run it.

### 2. Startup
1. Start the Django backend program. Initially, comment out the Django RBAC middleware. Then, refer to the documentation in the `rbac` folder to configure the system. Make sure you can create users and access the system. Configure your own initial data, such as users and permissions. After confirming that everything works, enable the RBAC middleware. Configure the Jetson device information and the frontend camera streams, RTSP URLs, or other media stream addresses (Remember to create the Jetson device first before adding frontend streaming information and other subsequent details).

2. Create a `local_settings` file in the same directory as the `settings` file. Configure routes, verification keys, and other information required for communication between the Jetson devices and Django. Configure device monitoring information for the platform to track the working status of edge devices.

3. Once the backend is running smoothly, double-click the one-click startup button on the frontend Jetson device. Start the server service first, then start the project service. You should see a popup window indicating that the services are running smoothly.

4. Monitor the backend for the status of frontend platform operations and video streaming usage. If everything is functioning correctly, the startup process is complete.

### Function Screenshots
![Screenshot 1](https://user-images.githubusercontent.com/40747806/135811154-7f8d59e9-669d-4311-ac43-7db687a3efb3.png)

![Screenshot 2](https://user-images.githubusercontent.com/40747806/135811268-f0e5a311-eadb-431f-8414-878c9e7313d7.png)

![Screenshot 3](https://user-images.githubusercontent.com/40747806/135811126-f041fb71-dca3-413e-9fe9-1b4f55f3c33b.png)

### Need Help?
You can contact the author to obtain the `sqlite3.db` file and directly access the system. If you need to use databases like MySQL or are unfamiliar with certain operations, you can contact the author via email: `18981275647@189.cn`

### Acknowledgments
Special thanks to [WuPeiqi](https://github.com/WuPeiqi).
