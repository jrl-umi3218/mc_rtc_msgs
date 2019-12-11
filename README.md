# mc\_rtc\_msgs

[![License](https://img.shields.io/badge/License-BSD%202--Clause-green.svg)](https://opensource.org/licenses/BSD-2-Clause)

This package provides ROS messages and services used by mc\_rtc's ROS plugin

# Installing

## Ubuntu LTS (16.04, 18.04, 20.04)

```bash
# Make sure you have required tools
sudo apt install apt-transport-https lsb-release ca-certificates gnupg
# Add our key
sudo apt-key adv --keyserver 'hkp://keyserver.ubuntu.com:80' --recv-key 892EA6EE273707C6495A6FB6220D644C64666806
# Add our repository (stable versions)
sudo sh -c 'echo "deb https://dl.bintray.com/gergondet/multi-contact-release $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/multi-contact.list'
# Use this to setup the HEAD version
# sudo sh -c 'echo "deb https://dl.bintray.com/gergondet/multi-contact-head $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/multi-contact.list'
# Update packages list
sudo apt update
# Install package
sudo apt install ros-${ROS_DISTRO}-mc-rtc-msgs
```

## Manually build from source

### Dependencies

To compile you need the following tools and libraries:

 * [Git]()
 * [CMake]() >= 2.8

### Building

Clone in your catkin workspace and build
