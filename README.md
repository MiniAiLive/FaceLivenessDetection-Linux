<div align="center">
   <h1> MiniAiLive Face Liveness Detection Windows SDK </h1>
   <img src=https://miniai.live/wp-content/uploads/2024/02/logo_name-1-768x426-1.png alt="MiniAiLive Logo"
   width="300">
</div>

## Welcome to the [MiniAiLive](https://www.miniai.live/)!
A 100% spoofing-prevention rate for both 3D printed and resin facial masks, confirms MiniAiLive® as a leading facial recognition solution for preventing biometric fraud in remote applications, such as online banking, requiring identity verification before granting access to sensitive data or valuable assets. Feel free to use our MiniAI 3D Face Passive Liveness Detection (face anti-spoofing) Linux SDK.

> **Note**
>
> SDK is fully on-premise, processing all happens on hosting server and no data leaves server.

## Table of Contents

- [Installation Guide](#installation-guide)
- [API Details](#api-details)
- [Gradio Demo](#gradio-demo)
- [Python Test API Example](#python-test-api-example)

## Installation Guide

### Prerequisites

- Python 3.6+
- Windows
- CPU: 2cores or more
- RAM: 4GB or more

### Installation Steps

1. **Download the Face Liveness Detection Windows Server Installer:**

   Download the Server installer for your operating system from the following link:
   
   [Download the On-premise Server Installer](https://drive.google.com/file/d/1FqCq7HWpI_NDodi9mmIb8aG7HNRzaMgB/view?usp=sharing)

2. **Install the On-premise Server:**

   Run the installer and follow the on-screen instructions to complete the installation.
   <div align="center">
      <img src="https://github.com/user-attachments/assets/3438fa1c-f869-4ac0-85fc-762716da09bc" width="450" />
   </div>

4. **Request License and Update:**

   Run MIRequest.exe file to generate a license request file. You can find it here.
   
   > C:\Users\Dev-1{Your User name}\AppData\Local\MiniAiLive\MiniAiLive-FaceLiveness-WinServer

   Open it, generate a license request file, and send it to us via email or WhatsApp. We will send the license based on your Unique Request file, then you can upload the license file to allow to use. Refer the below images.
   <div align="center">
      <img src="https://github.com/user-attachments/assets/d54686be-c7d8-42ba-8c57-f62fe1ec81e3" width="300" />
      <img src="https://github.com/user-attachments/assets/e33757a7-7fb1-411e-8136-129800198773" width="300" />
      <img src="https://github.com/user-attachments/assets/f34cdb2d-2b4e-48ec-b303-fd38cf128336" width="300" />
      <img src="https://github.com/user-attachments/assets/b1579722-462c-478a-9106-67b9a10b3514" width="300" />
   </div>

6. **Verify Installation:**

   After installation, verify that the On-premise Server is correctly installed by checking the task manager:
   <div align="center">
      <img src="https://github.com/user-attachments/assets/98e87782-073d-475c-962f-37151ef9754f" width="450" />
   </div>

## API Details

### Endpoint

- `POST http://127.0.0.1:8092/api/check_liveness` Face Liveness Detection API
- `POST http://127.0.0.1:8092/api/check_liveness_base64` Face Liveness Detection API

### Request

- **URL:** `http://127.0.0.1:8092/api/check_liveness`
- **Method:** `POST`
- **Form Data:**
  - `image`: The image file (PNG, JPG, etc.) to be analyzed. This should be provided as a file upload.
<div align="center">
   <img width="600" alt="Screenshot 2024-07-16 at 5 12 01 AM" src="https://github.com/user-attachments/assets/4a68a0b9-3299-4793-a76c-e8b9c6a7ed99">
</div>


- **URL:** `http://127.0.0.1:8092/api/check_liveness_base64`
- **Method:** `POST`
- **Raw Data:**
  - `JSON Format`:
    {
       "image": "--base64 image data here--"
    }
<div align="center">
   <img width="600" alt="Screenshot 2024-07-16 at 5 11 34 AM" src="https://github.com/user-attachments/assets/a67ea9b2-985a-4623-9b90-bc8ac1ed5c11">
</div>


### Response

The API returns a JSON object with the liveness result of the input face image. Here is an example response:
   <div align="center">
      <img src="https://github.com/user-attachments/assets/4a68a0b9-3299-4793-a76c-e8b9c6a7ed99" width="600" />
   </div>
   
## Gradio Demo

We have included a Gradio demo to showcase the capabilities of our Face Liveness Detection SDK. Gradio is a Python library that allows you to quickly create user interfaces for machine learning models.

### How to Run the Gradio Demo

1. **Install Gradio:**

   First, you need to install Gradio. You can do this using pip:

   ```sh
   git clone https://github.com/MiniAiLive/FaceLivenessDetection-Windows-SDK.git
   cd gradio
   pip install -r requirement.txt
   ```
2. **Run Gradio Demo:**
   ```sh
   python app.py
   ```
## Python Test API Example

To help you get started with using the API, here is a comprehensive example of how to interact with the Face Liveness Detection API using Python. You can use API with other language you want to use like C++, C#, Ruby, Java, Javascript and more

### Prerequisites

- Python 3.6+
- `requests` library (you can install it using `pip install requests`)

### Example Script

This example demonstrates how to send an image file to the API endpoint and process the response.

```python
import requests

# URL of the web API endpoint
url = 'http://127.0.0.1:8092/api/check_liveness'

# Path to the image file you want to send
image_path = './test_image.jpg'

# Read the image file and send it as form data
files = {'image': open(image_path, 'rb')}

try:
    # Send POST request
    response = requests.post(url, files=files)

    # Check if the request was successful
    if response.status_code == 200:
        print('Request was successful!')
        # Parse the JSON response
        response_data = response.json()
        print('Response Data:', response_data)
    else:
        print('Request failed with status code:', response.status_code)
        print('Response content:', response.text)

except requests.exceptions.RequestException as e:
    print('An error occurred:', e)
```

## Request license
Feel free to [Contact US](https://www.miniai.live/contact/)  to get a trial License. We are 24/7 online on WhatsApp: [+19162702374](https://wa.me/+19162702374).

## Contributing
Contributions are welcome! If you'd like to contribute to this project, please follow these steps:
```java 
1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them with descriptive messages.
4. Push your changes to your forked repository.
5. Submit a pull request to the original repository.
```
## Try Online Demo
Please visit our ID API Web Demo here. https://demo.miniai.live
<a href="https://demo.miniai.live" target="_blank">
  <img alt="" src="https://github.com/MiniAiLive/ID-DocumentRecognition-Windows-SDK/assets/127708602/15de62ae-1d5a-408f-9805-60e935da40b4">
</a>

## Related Product
No | Project | Feature
---|---|---|
1 | [FaceRecognition-LivenessDetection-Android-SDK](https://github.com/MiniAiLive/FaceRecognition-LivenessDetection-Android-SDK) | Face Matching, 3D Face Passive Liveness
2 | [FaceRecognition-LivenessDetection-iOS-SDK](https://github.com/MiniAiLive/FaceRecognition-LivenessDetection-iOS-SDK) | Face Matching, 3D Face Passive Liveness
3 | [FaceRecognition-LivenessDetection-Linux-SDK](https://github.com/MiniAiLive/FaceRecognition-LivenessDetection-Linux-SDK) | Face Matching, 3D Face Passive Liveness
4 | [FaceRecognition-LivenessDetection-Windows-SDK](https://github.com/MiniAiLive/FaceRecognition-LivenessDetection-Windows-SDK) | Face Matching, 3D Face Passive Liveness
5 | [FaceLivenessDetection-Android-SDK](https://github.com/MiniAiLive/FaceLivenessDetection-Android-SDK) | 3D Face Passive Liveness
6 | [FaceLivenessDetection-iOS-SDK](https://github.com/MiniAiLive/FaceLivenessDetection-iOS-SDK) | 3D Face Passive Liveness
7 | [FaceLivenessDetection-Linux-SDK](https://github.com/MiniAiLive/FaceLivenessDetection-Linux-SDK) | 3D Face Passive Liveness
8 | [FaceMatching-Android-SDK](https://github.com/MiniAiLive/FaceMatching-Android-SDK) | 1:1 Face Matching
9 | [FaceMatching-iOS-SDK](https://github.com/MiniAiLive/FaceMatching-iOS-SDK) | 1:1 Face Matching
10 | [FaceRecognition-Windows-Demo](https://github.com/MiniAiLive/FaceRecognition-Windows-Demo) | 1:1 Face Matching
11 | [FaceAttributes-Android-SDK](https://github.com/MiniAiLive/FaceAttributes-Android-SDK) | Face Attributes
12 | [ID-DocumentRecognition-Android-SDK](https://github.com/MiniAiLive/ID-DocumentRecognition-Android-SDK) | ID Document, Credit, MRZ Recognition
13 | [ID-DocumentRecognition-iOS-SDK](https://github.com/MiniAiLive/ID-DocumentRecognition-iOS-SDK) | ID Document, Credit, MRZ Recognition
14 | [ID-DocumentRecognition-Linux-SDK](https://github.com/MiniAiLive/ID-DocumentRecognition-Linux-SDK) | ID Document, Credit, MRZ Recognition
15 | [ID-DocumentRecognition-Windows-SDK](https://github.com/MiniAiLive/ID-DocumentRecognition-Windows-SDK) | ID Document, Credit, MRZ Recognition

## About MiniAiLive
[MiniAiLive](https://www.miniai.live/) is a leading AI solutions company specializing in computer vision and machine learning technologies. We provide cutting-edge solutions for various industries, leveraging the power of AI to drive innovation and efficiency.

## Contact US
For any inquiries or questions, please [Contact US](https://www.miniai.live/contact/)

<p align="center">
<a target="_blank" href="https://t.me/Contact_MiniAiLive"><img src="https://img.shields.io/badge/telegram-@MiniAiLive-blue.svg?logo=telegram" alt="www.miniai.live"></a>&emsp;
<a target="_blank" href="https://wa.me/+19162702374"><img src="https://img.shields.io/badge/whatsapp-MiniAiLive-blue.svg?logo=whatsapp" alt="www.miniai.live"></a>&emsp;
<a target="_blank" href="https://join.skype.com/invite/ltQEVDmVddTe"><img src="https://img.shields.io/badge/skype-MiniAiLive-blue.svg?logo=skype" alt="www.miniai.live"></a>&emsp;
</p>
