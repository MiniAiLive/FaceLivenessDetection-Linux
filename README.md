<div align="center">
   <h1>Face Liveness Detection Linux SDK</h1>
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

## Face-LivenessSDK Installation Guide

### Prerequisites

- Python 3.6+
- Linux
- CPU: 2 cores or more
- RAM: 8 GB or more

### Installation Steps

1. **Download the Face Liveness Detection Linux Server Installer:**

   Download the Server installer for your operating system from the following link:
   
   [Download the On-premise Server Installer](https://drive.google.com/file/d/1nFxftQYJPh-BJ5NRiIaAG5d9bC5Ydo5E/view?usp=sharing)

2. **Install the On-premise Server:**

   Run the installer and follow the on-screen instructions to complete the installation. Go to the Download folder and run this command.
   ```sh
   $ cd Download
   $ sudo dpkg -i --force-overwrite MiniAiLive-FaceLiveness-LinuxServer.deb
   ```
<div align="center">
   <img src=https://github.com/user-attachments/assets/01507acf-cca0-43c7-91f8-f9605805219b alt="MiniAiLive Installer">
</div>

   You can refer our Documentation here. https://docs.miniai.live

3. **Request License and Update:**

   You can generate the License Request file by using this command:
   ```sh
   $ cd /opt/mini-faceliveness/
   $ sudo ./MiRequest request /home/ubuntu/Download/trial_request.miq
   ```
<div align="center">
   <img src=https://github.com/user-attachments/assets/f5204c7b-af9d-448b-a23c-ee743271bff4 alt="MiniAiLive Installer">
</div>

   Then you can see the license request file on your directory, and send it to us via email or WhatsApp. We will send the license based on your Unique Request file, then you can upload the license file to allow to use. Refer the below images.
   
   ```sh
   $ sudo ./MiRequest update /home/ubuntu/Download/Faceliveness_trial_linux.mis
   ```
<div align="center">
   <img src=https://github.com/user-attachments/assets/beb4aedc-fe98-4803-9b9c-a62d749cf1f3 alt="MiniAiLive Installer">
</div>

4. **Verify Installation:**

   After installation, verify that the On-premise Server is correctly installed by using this command:
   ```sh
   $ systemctl list-units --state running
   ```
   If you can see 'Mini-faceliveness-svc.service', the server has been installed successfully. Refer the below image.
<div align="center">
   <img src=https://github.com/user-attachments/assets/af1d7c37-62af-4191-bbc0-d57745c89362 alt="MiniAiLive Installer">
</div>

## Face-LivenessSDK API Details

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
   git clone https://github.com/MiniAiLive/FaceLivenessDetection-Linux.git
   pip install -r requirement.txt
   cd gradio
   ```
2. **Run Gradio Demo:**
   ```sh
   python app.py
   ```
## Python Test API Example

To help you get started with using the API, here is a comprehensive example of how to interact with the Face Liveness Detection API using Python. You can use API with another language you want to use like C++, C#, Ruby, Java, Javascript, and more

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
Feel free to [Contact US](https://www.miniai.live/contact/) to get a trial License. We are 24/7 online on [WhatsApp](https://wa.me/+19162702374).


## Face & IDSDK Online Demo, Resources
<div style="display: flex; justify-content: center; align-items: center;"> 
   <table style="text-align: center;">
      <tr>
         <td style="text-align: center; vertical-align: middle;"><a href="https://github.com/MiniAiLive"><img src="https://miniai.live/wp-content/uploads/2024/10/new_git-1-300x67.png" style="height: 60px; margin-right: 5px;" title="GITHUB"/></a></td> 
         <td style="text-align: center; vertical-align: middle;"><a href="https://huggingface.co/MiniAiLive"><img src="https://miniai.live/wp-content/uploads/2024/10/new_hugging-1-300x67.png" style="height: 60px; margin-right: 5px;" title="HuggingFace"/></a></td> 
         <td style="text-align: center; vertical-align: middle;"><a href="https://demo.miniai.live"><img src="https://miniai.live/wp-content/uploads/2024/10/new_gradio-300x67.png" style="height: 60px; margin-right: 5px;" title="Gradio"/></a></td> 
      </tr> 
      <tr>
         <td style="text-align: center; vertical-align: middle;"><a href="https://docs.miniai.live/"><img src="https://miniai.live/wp-content/uploads/2024/10/a-300x70.png" style="height: 60px; margin-right: 5px;" title="Documentation"/></a></td> 
         <td style="text-align: center; vertical-align: middle;"><a href="https://www.youtube.com/@miniailive"><img src="https://miniai.live/wp-content/uploads/2024/10/Untitled-1-300x70.png" style="height: 60px; margin-right: 5px;" title="Youtube"/></a></td> 
         <td style="text-align: center; vertical-align: middle;"><a href="https://play.google.com/store/apps/dev?id=5831076207730531667"><img src="https://miniai.live/wp-content/uploads/2024/10/googleplay-300x62.png" style="height: 60px; margin-right: 5px;" title="Google Play"/></a></td>
      </tr>
   </table>
</div>

## Our Products
| No | Project | Features |
|----|---------|-----------|
| 1  | [FaceRecognition-Docker](https://github.com/MiniAiLive/FaceRecognition-Docker) | 1:1 & 1:N Face Matching |
| 2  | [FaceRecognition-Windows](https://github.com/MiniAiLive/FaceRecognition-Windows) | 1:1 & 1:N Face Matching |
| 3  | [FaceRecognition-Linux](https://github.com/MiniAiLive/FaceRecognition-Linux) | 1:1 & 1:N Face Matching |
| 4  | [FaceRecognition-LivenessDetection-Android](https://github.com/MiniAiLive/FaceRecognition-LivenessDetection-Android) | 1:1 & 1:N Face Matching, 2D & 3D Face Passive Liveness Detection |
| 5  | [FaceRecognition-LivenessDetection-iOS](https://github.com/MiniAiLive/FaceRecognition-LivenessDetection-iOS) | 1:1 & 1:N Face Matching, 2D & 3D Face Passive Liveness Detection |
| 6  | [FaceRecognition-LivenessDetection-CPP](https://github.com/MiniAiLive/FaceRecognition-LivenessDetection-CPP) | 1:1 & 1:N Face Matching, 2D & 3D Face Passive Liveness Detection |
| 7  | [FaceLivenessDetection-Docker](https://github.com/MiniAiLive/FaceLivenessDetection-Docker) | 2D & 3D Face Passive Liveness Detection |
| 8  | [FaceLivenessDetection-Windows](https://github.com/MiniAiLive/FaceLivenessDetection-Windows) | 2D & 3D Face Passive Liveness Detection |
| 9  | [FaceLivenessDetection-Linux](https://github.com/MiniAiLive/FaceLivenessDetection-Linux) | 2D & 3D Face Passive Liveness Detection |
| 10  | [FaceLivenessDetection-Android](https://github.com/MiniAiLive/FaceLivenessDetection-Android) | 2D & 3D Face Passive Liveness Detection |
| 11  | [FaceLivenessDetection-iOS](https://github.com/MiniAiLive/FaceLivenessDetection-iOS) | 2D & 3D Face Passive Liveness Detection |
| 12 | [FaceAttributes-Android](https://github.com/MiniAiLive/FaceAttributes-Android) | Face Attributes, Age & Gender Estimation |
| 13 | [FaceMatching-Android](https://github.com/MiniAiLive/FaceMatching-Android) | 1:1 Face Matching |
| 14 | [FaceMatching-WinApp](https://github.com/MiniAiLive/FaceMatching-WinApp) | 1:1 Face Matching |
| 15 | [ID-DocumentRecognition-Docker](https://github.com/MiniAiLive/ID-DocumentRecognition-Docker) | ID Card, Passport, Driver License, Credit Card, MRZ Recognition |
| 16 | [ID-DocumentRecognition-Windows](https://github.com/MiniAiLive/ID-DocumentRecognition-Windows) | ID Card, Passport, Driver License, Credit Card, MRZ Recognition |
| 17 | [ID-DocumentRecognition-Linux](https://github.com/MiniAiLive/ID-DocumentRecognition-Linux) | ID Card, Passport, Driver License, Credit Card, MRZ Recognition |
| 18 | [ID-DocumentRecognition-Android](https://github.com/MiniAiLive/ID-DocumentRecognition-Android) | ID Card, Passport, Driver License, Credit Card, MRZ Recognition |
| 19 | [ID-DocumentLivenessDetection-Docker](https://github.com/MiniAiLive/ID-DocumentLivenessDetection-Docker) | ID Document Liveness Detection |
| 20 | [ID-DocumentLivenessDetection-Windows](https://github.com/MiniAiLive/ID-DocumentLivenessDetection-Windows) | ID Document Liveness Detection |
| 21 | [ID-DocumentLivenessDetection-Linux](https://github.com/MiniAiLive/ID-DocumentLivenessDetection-Linux) | ID Document Liveness Detection |

## About MiniAiLive
[MiniAiLive](https://www.miniai.live/) is a leading AI solutions company specializing in computer vision and machine learning technologies. We provide cutting-edge solutions for various industries, leveraging the power of AI to drive innovation and efficiency.

## Contact US
For any inquiries or questions, please contact us on [WhatsApp](https://wa.me/+19162702374).

<p align="center">
<a target="_blank" href="https://t.me/Contact_MiniAiLive"><img src="https://img.shields.io/badge/telegram-@MiniAiLive-blue.svg?logo=telegram" alt="www.miniai.live"></a>&emsp;
<a target="_blank" href="https://wa.me/+19162702374"><img src="https://img.shields.io/badge/whatsapp-MiniAiLive-blue.svg?logo=whatsapp" alt="www.miniai.live"></a>&emsp;
</p>
