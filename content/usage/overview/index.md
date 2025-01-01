+++
title = "Overview"
description = "Cockpit overview."
date = 2024-09-03T04:30:00+10:00
template = "docs/page.html"
sort_by = "weight"
weight = 0
draft = false

[extra]
lead = 'Cockpit is an intuitive and customizable cross-platform control station software for remote vehicles of all types.'
toc = true
top = false
+++

{{ easy_image(src="cockpit-banner", width=460, center=true) }}

{{ easy_image(src="interface-highlight", width=650, center=true) }}

## A bit of context...

The existing market for control station software is missing an option that's readily available, easy to use, versatile, easy to customise and develop for, and cross-platform. In response to this need, and fueled by years of inspirations for what a truly great control station could be, Cockpit is Blue Robotics' next-generation control interface, for thrusting your vehicle control experience into the future.

## Availability and Limitations

[Cockpit is open source](https://github.com/bluerobotics/cockpit), and is free to install and use.

It is currently available as: 
1. [a BlueOS Extension](https://docs.bluerobotics.com/BlueOS-Extensions-Repository#:~:text=Cockpit,-Maintainer) (requires BlueOS >= 1.1)
   - with an interface that runs in a web browser, on almost any web-capable device (including mobiles and VR headsets)
1. [a standalone application](../installation#self-contained-application)
   - built for Windows, macOS, and Linux (including SteamOS)
      - we are looking into also making it available on iOS and android
   - includes some additional features, and may run more reliably
   - if connected to a non-BlueOS vehicle, requires external server software to communicate in the formats it expects
      - e.g. [MAVLink Server](https://github.com/bluerobotics/mavlink-server)
        and [MAVLink Camera Manager](https://github.com/mavlink/mavlink-camera-manager)

### Try it!

0. ⏯️ [Watch the usage introduction video](#usage-introduction-video)
1. 🌐 [Run a browser-served version](https://docs.bluerobotics.com/cockpit), to play with the latest state of the interface
   - Opens instantly
   - Has no vehicle connected, so widgets don't display meaningful data
1. 🎮 [Run a full vehicle simulation with BlueOS](https://blueos.cloud/bluesim), to test the control process and effectiveness of different views
   - Can take several minutes to start and connect to the virtual machine
   - Can get behind on updates, so may not be running the latest Cockpit and/or BlueOS version
1. 🚀 [Install your own copy](../installation)

## Primary Feature List

- Browser-based control station software, for vehicle control and monitoring from any web-capable device
- Widget-based layout system, with freeform positioning and resizing
- Custom display [Views](../advanced/#views), for interface pages/profiles that can be switched between
    - Different browser windows/screens/devices can independently select which view to display
    - Views are downloadable and can be shared (json contains name and list of components and widget settings)
- MAVLink `NAMED_VALUE_FLOAT`/`_INT` messages are self-registering for use in [mini-widgets](../advanced/#mini-widgets) (including custom ones!)
- WebRTC-based [video widget](../advanced/#video)
    - Multiple widgets can be added to support arbitrary numbers of video streams
    - Includes video recording support, on the display device
- [Map widget](../advanced/#map)
    - Provides position tracking
    - Allows planning (and saving/loading) autonomous missions
    - Allows mission control
    - In future will allow setting the current vehicle position, and clicking to guide the vehicle to new positions
- Customisable Actions mappable to user inputs (e.g. joysticks, and key presses / screen clicks in future)
    - Actions can send commands to the vehicle, or can trigger local events like view switching and starting video recording
    - Includes support for simultaneous input from multiple sources (including multiple joysticks)
- [Joysticks](../advanced/#joysticks) of _any_ type can be configured
    - Buttons and axes can be mapped to arbitrary Actions
- [Notification system](../advanced/#alerts)
    - Displays autopilot (MAVLink `STATUSTEXT`) and application alerts
    - Includes text to speech announcements
- [Mission naming](../advanced/#mission-name) used on the interface and video save filenames

## Community

### Discussions and Support

- [Discussion Forum](https://discuss.bluerobotics.com/c/bluerobotics-software/cockpit/91)
- [Issues and Feature Requests](https://github.com/bluerobotics/cockpit/issues)
- [Chat (Discord)](https://discord.gg/mFgvxhCDrv)

### Usage Introduction Video
`Phil Parisi (October 2024) - Supported by Blue Robotics`
<iframe width="560" height="315" src="https://www.youtube.com/embed/1bpTAEN3K3s" title="YouTube video player" frameborder="0" allow="encrypted-media;" allowfullscreen></iframe>

### Developer Presentations
`ArduPilot Developers Conference (October 2024)`
<iframe width="560" height="315" src="https://www.youtube.com/embed/IbfDEuGvlmo" title="YouTube video player" frameborder="0" allow="encrypted-media;" allowfullscreen></iframe>
