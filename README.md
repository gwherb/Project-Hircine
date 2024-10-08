<a id="readme-top"></a>

[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![LinkedIn][garrett-linkedin-shield]][garrett-linkedin-url]


<!-- PROJECT LOGO -->
<br />
<div align="center">
  <a href="https://github.com/gwherb/Project-Hircine">
    <img src="images/logo.png" alt="Logo" width="180" height="180">
  </a>

<h3 align="center">Project Hircine</h3>
</div>


<!-- ABOUT THE PROJECT -->
## About The Project

<!-- [![Product Name Screen Shot][product-screenshot]](https://example.com) -->
### Project Description

This project set out to design computer vision software for compact drones to assist ground soldiers with walk ins. The software utilizes YOLO for object detection and Google's Hitnet model for stereovision depth. With these technologies, an objects position relative to a drone can be found. Our program also seeks to communicate a detected objects information to a TAK server.

In addition to the initial project vision above, we created an program to Render detections from the drone from the point of view of an external device. This acts as "wallhacks" for the external viewer.

The object detection was done on a raspberry pi for its cheap cost to make producing these drones scalable. Depth detection and server hosting was done on a laptop with the compute power to quickly perform depth calculations. We used ATAK for our TAK communications as an Android devices is the most realistic platform that our TAK communications will go to.

For a more detailed description of some of our Technology motivations, see ```Technology Motivations.pdf```

### Built With

* [![Flask][Flask]][Flask-url]
* [![Ultralytics][Ultralytics.com]][Ultralytics-url]
* [![Docker][Docker]][Docker-url]
* [![PyTak][PyTak.com]][PyTak-url]
* [![TAK][TAK.gov]][TAK-url]



<!-- GETTING STARTED -->
## Getting Started

In this repo, we have broken down the project into a couple parts:

**Training:** Files for training and tuning of the object detection model

**Raspberry Pi Files:** Files for both the detector and external viewer

**Server Hosting:** Files for hosting the server to facilitate communication between devices as well as perform depth detection on incoming object detections

**TAK Utilities:** Files for communicating with an ATAK client

<!-- Setup -->
## Setup

**Detector hardware requirements:** Raspberry Pi (64 bit Bookworm), 2 x RPi Camera Modules, qmc5883l compass module

**Viewer hardware requirements:** Raspberry Pi (64 bit Bookworm), 1 x RPi Camera Modules, qmc5883l compass module, RPi 7 inch touch screen (for mobile viewing)


**Once all hardware is setup:**
1. Initliaize Flask server: ```python flask_host.py```
2. Start up detector on detector RPi: ```python server_posting.py```
3. Send information detections to TAK client and viewer RPi by sending a GET request to @/lat_lon
4. To view objects on the viewer RPi: ```python pi_viewer.py```

**Compass Installation:** See [py_qmc5883l](https://github.com/RigacciOrg/py-qmc5883l) for compass module instructions

<p align="right">(<a href="#readme-top">back to top</a>)</p>

 

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/gwherb/Project-Hircine.svg?style=for-the-badge
[contributors-url]: https://github.com/gwherb/Project-Hircine/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/gwherb/Project-Hircine.svg?style=for-the-badge
[forks-url]: https://github.com/gwherb/Project-Hircine/network/members
[stars-shield]: https://img.shields.io/github/stars/gwherb/Project-Hircine.svg?style=for-the-badge
[stars-url]: https://github.com/gwherb/Project-Hircine/stargazers
[issues-shield]: https://img.shields.io/github/issues/gwherb/Project-Hircine.svg?style=for-the-badge
[issues-url]: https://github.com/gwherb/Project-Hircine/issues
[license-shield]: https://img.shields.io/github/license/gwherb/Project-Hircine.svg?style=for-the-badge
[license-url]: https://github.com/gwherb/Project-Hircine/blob/master/LICENSE.txt
[solan-linkedin-shield]: https://img.shields.io/badge/-Solan's_LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[garrett-linkedin-shield]: https://img.shields.io/badge/-Garrett's_LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[solan-linkedin-url]: https://www.linkedin.com/in/solan-degefa-714648195/
[garrett-linkedin-url]: https://www.linkedin.com/in/garrett-herb-5647b0217/
[product-screenshot]: images/screenshot.png
[PyTak.com]: https://img.shields.io/badge/PyTak-4051B5?style=for-the-badge&logo=PyTak&logoColor=white
[PyTak-url]: https://pytak.readthedocs.io/en/latest/
[Ultralytics.com]: https://img.shields.io/badge/Ultralytics-0B38AD?style=for-the-badge&logo=Ultralytics&logoColor=white
[Ultralytics-url]: https://docs.ultralytics.com
[Docker]: https://img.shields.io/badge/docker-0db7ed?style=for-the-badge&logo=docker&logoColor=white
[Docker-url]: https://www.docker.com/
[Flask]: https://img.shields.io/badge/flask-000000?style=for-the-badge&logo=flask&logoColor=white
[Flask-url]: https://pytak.readthedocs.io/en/latest/
[TAK.gov]: https://img.shields.io/badge/tak-18191B?style=for-the-badge&logo=tak&logoColor=white
[TAK-url]: https://tak.gov/
 
