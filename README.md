# Jetson Fit

In order to keep my kids doing exercise during the shelter-in-place order, we started playing [Nintendo Ring Fit Adventure](https://ringfitadventure.nintendo.com/). Thanks a lot Nintendo :+1: !

It is an awesome exercise based game.
However, after three months and leveling up over 200, the kids started losing interest.

We moved on to play [Mario & Sonic at the Olympic Games Tokyo 2020](https://www.nintendo.com/games/detail/mario-and-sonic-at-the-olympic-games-tokyo-2020-switch/) and [Yoshi's Crafted World](https://yoshiscraftedworld.nintendo.com/).
Unfortunately, these games are not exercise based and only some sport events support motion control.
In particular, my 3 yr old kid's finger is not developed enough to play with the key pad.

So this hack is created, for converting games into motion controllable one for small kids.

# Demo

[![Demo](https://img.youtube.com/vi/P9RO0Vl4jNA/0.jpg)](https://youtu.be/P9RO0Vl4jNA)

- [Yoshi's Crafted World](https://yoshiscraftedworld.nintendo.com/)

[![Demo](https://img.youtube.com/vi/gId1TodtYOY/0.jpg)](https://youtu.be/gId1TodtYOY)

- [Mario & Sonic at the Olympic Games Tokyo 2020](https://www.nintendo.com/games/detail/mario-and-sonic-at-the-olympic-games-tokyo-2020-switch/) - Karate

# Hardware

- [Nvidia Jetson NX](https://www.nvidia.com/en-us/autonomous-machines/embedded-systems/jetson-xavier-nx/)
- Logitech C920 at 30fps
- Nintendo Switch

# Design

![Design](https://github.com/singyiu/jetsonfit/blob/master/design.png?raw=true)

# Prerequisites

1. TensorRT Pose Estimation
https://github.com/NVIDIA-AI-IOT/trt_pose

2. Joycontrol
https://github.com/mart1nro/joycontrol

3. Jupyter Notebook

# Setup
1. Install trt_pose from https://github.com/NVIDIA-AI-IOT/trt_pose
2. Install joycontrol from https://github.com/mart1nro/joycontrol
3. Clone this repo
4. Download this weights [resnet18_baseline_att_224x224_A (81MB)](https://drive.google.com/open?id=1XYDdCUdiF2xxx4rznmLb62SdOUZuoNbd) and save it in the trt_pose folder
5. Install jupyter
6. Open [trt_pose/live_demo_karate.ipynb](trt_pose/live_demo_karate.ipynb) with jupyter notebook and follow the notes
7. Start joycontrol tcp server with
```
sudo python3 joycontrol/run_controller_server.py
OR
sudo python3 joycontrol/run_controller_server.py PRO_CONTROLLER -r <your Switch's BLE MAC address>
```
