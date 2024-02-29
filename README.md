<div align="center">
   <h1> MiniAiLive Face LivenessDetection Server SDK </h1>
   <img src=https://www.miniai.live/wp-content/uploads/2023/03/logo_name-1-768x426.png alt="MiniAiLive Logo"
   width="300">
</div>

## Welcome to the [MiniAiLive](https://www.miniai.live/)!
A 100% spoofing-prevention rate for both 3D printed and resin facial masks, confirms MiniAiLive® as a leading facial recognition solution for preventing biometric fraud in remote applications, such as online banking, requiring identity verification before granting access to sensitive data or valuable assets.
Feel free to use our MiniAI 3D Face Passive Liveness Detection (face anti-spoofing) Server SDK.

> **Note**
>
> SDK is fully on-premise, processing all happens on hosting server and no data leaves server.

## Project Structure
```graphql
# Code & components for pages
./MiniAI-Face-LivenessDetection-ServerSDK
  ├─ bin/linux_x86_64                 - # Core library files
  │  ├─ libminiai_liveness.so
  │  ├─ libminiai_models.so
  │  └─ libimutils.so
  ├─ cpp                              - # C++ example
  │  ├─ CMakeLists.txt                - # CMake file for build example
  │  ├─ miniai_liveness.h             - # C++ header file to include library
  │  └─ main.cpp                      - # C++ example code
  ├─ flask                            - # Python flask API serving example
  │  ├─ app.py                        - # Flask example code
  │  └─ requirements.txt               - # Python requirement list
  ├─ model                            - # NN dictionary files for library
  │  ├─ data1.bin
  │  └─ data2.bin
  ├─ python                           - # Python example
  │  ├─ miniai_liveness.py            - # Python library Import Interface file
  │  ├─ main.py                       - # Python example code
  │  └─ requirements.txt              - # Python requirement list
  ├─ test_image                       - # Test Images
  │  ├─ genuine.jpg
  │  └─ spoof.png
  └─ Dockerfile                       - # Docker script for python flask API serving example
```

## Setup Project
#### - Linux
- Download repo and extract it
```
git clone https://github.com/MiniAiLive/MiniAI-Face-LivenessDetection-ServerSDK.git
```
- Install system dependencies
```
sudo apt-get update -y
sudo apt-get install -y libcurl4-openssl-dev libssl-dev libopencv-dev
```
- Copy libraries into system folder
```
cp ./bin/linux_x86_64/libminiai_models.so /usr/lib
cp ./bin/linux_x86_64/libimutils.so /usr/lib
```

#### - Windows
[Contact US](https://www.miniai.live/contact/) by Email info@miniai.live
  
## C++ Example
- Replace license key in main.cpp
- Build project
```
cd cpp
mkdir build && cd build
cmake ..
make
```
- Run project
```
./example_liveness --image ../../test_image/spoof.png --model ../../model
```

## Python Example
- Replace license key in main.py
- Install dependencies
```
cd python
pip install -r requirements.txt
```
- Run project
```
python main.py
```
## Python Flask Example
- Replace license key in app.py
- Install dependencies
```
cd flask
pip install -r requirements.txt
```
- Run project
```
python app.py
```
<p align="center">
  <img width="360" src="https://github.com/MiniAiLive/MiniAI-Face-LivenessDetection-ServerSDK/assets/153516004/2254e5a7-a647-4a6b-99ab-1ad631c8266d">&emsp;&emsp;
  <img width="360" src="https://github.com/MiniAiLive/MiniAI-Face-LivenessDetection-ServerSDK/assets/153516004/fdd16c8e-b90e-4fa0-a304-aa5f287cb506">
</p>

## Docker Flask Example
- Replace license key in app.py
- Build docker image
```
docker build --pull --rm -f "Dockerfile" -t miniailiveness:latest "."
```
- Run image
```
docker run --network host miniailiveness
```

## Request license
Feel free to [Contact US](https://www.miniai.live/contact/)  to get trial License   
You will get email with trial license key ("XXXXX-XXXXX-XXXXX-XXXXX").

## Contributing
Contributions are welcome! If you'd like to contribute to this project, please follow these steps:
```java 
1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Make your changes and commit them with descriptive messages.
4. Push your changes to your forked repository.
5. Submit a pull request to the original repository.
```
### Related Product
No | Project | Feature
---|---|---|
1 | [MiniAI-Face-Recognition-AndroidSDK](https://github.com/MiniAiLive/MiniAI-Face-Recognition-AndroidSDK) | Face Matching, 3D Face Passive Liveness
2 | [MiniAI-Face-Recognition-iOS-SDK](https://github.com/MiniAiLive/MiniAI-Face-Recognition-iOS-SDK) | Face Matching, 3D Face Passive Liveness
3 | [MiniAI-Face-Recognition-ServerSDK](https://github.com/MiniAiLive/MiniAI-Face-Recognition-ServerSDK) | Face Matching, 3D Face Passive Liveness
4 | [MiniAI-Face-Recognition-WindowsSDK](https://github.com/MiniAiLive/MiniAI-Face-Recognition-WindowsSDK) | Face Matching, 3D Face Passive Liveness
5 | [MiniAI-Face-LivenessDetection-AndroidSDK](https://github.com/MiniAiLive/MiniAI-Face-LivenessDetection-AndroidSDK) | 3D Face Passive Liveness
6 | [MiniAI-Face-LivenessDetection-iOS-SDK](https://github.com/MiniAiLive/MiniAI-Face-LivenessDetection-iOS-SDK) | 3D Face Passive Liveness
7 | [MiniAI-Face-LivenessDetection-ServerSDK](https://github.com/MiniAiLive/MiniAI-Face-LivenessDetection-ServerSDK) | 3D Face Passive Liveness
8 | [MiniAI-Face-Matching-AndroidSDK](https://github.com/MiniAiLive/MiniAI-Face-Matching-AndroidSDK) | 1:1 Face Matching
9 | [MiniAI-Face-Matching-iOS-SDK](https://github.com/MiniAiLive/MiniAI-Face-Matching-iOS-SDK) | 1:1 Face Matching
10 | [MiniAI-Face-Attributes-AndroidSDK](https://github.com/MiniAiLive/MiniAI-Face-Attributes-AndroidSDK) | Face Attributes

## About MiniAiLive
[MiniAiLive](https://www.miniai.live/) is a leading AI solutions company specializing in computer vision and machine learning technologies. We provide cutting-edge solutions for various industries, leveraging the power of AI to drive innovation and efficiency.

## Contact US
For any inquiries or questions, please [Contact US](https://www.miniai.live/contact/)

<p align="center">
<a target="_blank" href="https://t.me/Contact_MiniAiLive"><img src="https://img.shields.io/badge/telegram-@MiniAiLive-blue.svg?logo=telegram" alt="www.miniai.live"></a>&emsp;
<a target="_blank" href="https://wa.me/+19162702374"><img src="https://img.shields.io/badge/whatsapp-MiniAiLive-blue.svg?logo=whatsapp" alt="www.miniai.live"></a>&emsp;
<a target="_blank" href="https://join.skype.com/invite/ltQEVDmVddTe"><img src="https://img.shields.io/badge/skype-MiniAiLive-blue.svg?logo=skype" alt="www.miniai.live"></a>&emsp;
</p>
