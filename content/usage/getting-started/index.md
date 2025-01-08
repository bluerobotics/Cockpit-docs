+++
title = "Getting Started"
description = "Cockpit getting started instructions."
date = 2025-01-08T21:05:00+11:00
template = "docs/page.html"
sort_by = "weight"
weight = 20
draft = false

[extra]
lead = ''
toc = true
top = false
+++
## Welcome to Cockpit!

When you're first starting out, it's good to find out what there is and where you can find it.
On the first boot, Cockpit opens a tutorial window that walks you through the main parts of the interface:

{{ easy_image(src="tutorial", width=500, center=true) }}

## General Configuration

Cockpit generally automatically finds and/or connects to your vehicle:
- When run as a BlueOS Extension, Cockpit will automatically be configured to connect using the IP address of the connection to BlueOS.
- When run as a standalone application, there is a vehicle discovery process for detecting BlueOS vehicles on your network:
{{ easy_image(src="vehicle-discovery", width=400, center=true) }}

If that address changes while operating, or your vehicle is not running BlueOS, it may be necessary to configure the global vehicle
address, and potentially also the more specific backend server addresses to connect to MAVLink2REST and the WebRTC video signalling
server (e.g. from MAVLink Camera Manager), so that Cockpit knows the correct connection points for the vehicle.

To access the configuration section, open the left sidebar, and select `Settings / General`:

{{ easy_image(src="general-config", width=500, center=true) }}

If necessary, there are some additional details [in the advanced usage documentation](../advanced/#general).

## Interface Setup

### Visual Display

Once connected to a vehicle, Cockpit loads a [profile](../advanced/#profiles) with a default set of interface 
[views](../advanced/#views) that are relevant for the vehicle type. These should serve as a reasonable starting
point, which you can then [customise](../advanced/#edit-mode) to suit your specific use-cases and preferences.

#### MAVs / QuadCopters

Micro-aerial vehicles start out with an interface similar to other control station softwares, with
- a map
- basic tracking of the connection details and notifications
- on-screen control options to arm, take off, and change flight modes, and
- some telemetry widgets to track the vehicle altitude and attitude

{{ easy_image(src="mav-map-view", width=600, center=true) }}

#### Rovers / Boats

The default interface for rovers and boats is similar to the MAV one, but with the bottom bar altitude tracking
swapped for a GPS speed widget:

{{ easy_image(src="boat-map-view", width=600, center=true) }}

#### ROVs / Submarines

Cockpit was first developed for ROVs, and there are three starting views built in:

1. Video view
    - Includes a video stream, vehicle telemetry, compass and attitude instrument indicators, status updates, and flight mode selection
    - Useful for first-person control, focused on what the vehicle can see

{{ easy_image(src="sub-video-view", width=600, center=true) }}

2. HUD view
    - Includes a video stream, vehicle telemetry, heads-up display (HUD) overlay elements, status updates, and flight mode selection
    - An alternative for first-person control of a vehicle, focused on precision maneuvering

{{ easy_image(src="sub-hud-view", width=600, center=true) }}

3. Map view
    - Includes a map, vehicle telemetry, status updates, and flight mode selection
    - Most useful for mission planning and remote monitoring of vehicles with a positioning system and/or autonomous control

{{ easy_image(src="sub-map-view", width=600, center=true) }}

### Joystick Configuration
For vehicles controlled via a joystick, [button and axis function mappings](../advanced/#joysticks) can be set through the
`Settings / Joystick` section of the left sidebar:

{{ easy_image(src="joystick-config", width=500, center=true) }}

## Vehicle Setup

Cockpit does not currently contain vehicle configuration or calibration functionalities. It is recommended to perform these in advance,
using either [the BlueOS web interface](https://blueos.cloud/docs/latest/usage/advanced/#vehicle-setup) and/or an alternative control
station software like QGroundControl.

## Operation

Once you're ready to operate your vehicle, you can get started with remote control, or switch between the
[Mission Planning](../advanced/#mission-planning) and Flight displays via the left sidebar.
