# mc\_rtc\_msgs

[![License](https://img.shields.io/badge/License-BSD%202--Clause-green.svg)](https://opensource.org/licenses/BSD-2-Clause)
[![Hosted By: Cloudsmith](https://img.shields.io/badge/OSS%20hosting%20by-cloudsmith-blue?logo=cloudsmith)](https://cloudsmith.com)

This package provides ROS messages and services used by mc\_rtc's ROS plugin

# Installing

## Ubuntu LTS (16.04, 18.04, 20.04)

You must first setup our package mirror:

```
curl -1sLf \
  'https://dl.cloudsmith.io/public/mc-rtc/stable/setup.deb.sh' \
  | sudo -E bash
```

You can also choose the head mirror which will have the latest version of this package:

```
curl -1sLf \
  'https://dl.cloudsmith.io/public/mc-rtc/stable/setup.deb.sh' \
  | sudo -E bash
```

You can then install the package:

```bash
sudo apt install ros-${ROS_DISTRO}-mc-rtc-msgs
```

## Manually build from source

### Dependencies

To compile you need the following tools and libraries:

 * [Git]()
 * [CMake]() >= 2.8

### Building

Clone in your catkin workspace and build
