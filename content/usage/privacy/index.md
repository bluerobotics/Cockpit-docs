+++
title = "Data Privacy"
description = "Cockpit data collection and usage documentation."
date = 2025-07-12T05:50:00+08:00
template = "docs/page.html"
sort_by = "weight"
weight = 40
draft = false

[extra]
lead = ''
toc = true
top = false
+++

## Context

Any device which connects to the internet provides some information about itself and its user in doing so. How that information is processed, stored, and used determine whether it is a potential privacy concern.

As open source software, Cockpit can be freely independently reviewed and audited for privacy risks, and we encourage users to educate themselves on what data is exposed through connecting your vehicle to the internet and making use of the services within Cockpit.

## Intent

1. Anonymous usage data and statistics are collected to inform the development direction, identify problems within Cockpit, and share insights with the community
1. No data is collected for or sold to advertisers

## Data Collection and Usage Details

### Automatic Events

| Service | Domain | Data | Usage |
| --- | --- | --- | --- |
| [Error statistics and tracebacks](https://github.com/bluerobotics/cockpit/blob/master/src/main.ts) | sentry.io | - IP address<br>- Cockpit version<br>- Error tracebacks | - tracking error rates and reasons<br>- estimating proportions of in-use Cockpit versions<br>- samples removed after 90 days<br>- collection limited to tagged releases of Cockpit (e.g. not development branches) |
| [Usage events and statistics](https://github.com/search?q=repo%3Abluerobotics%2Fcockpit+eventTracker.capture&type=code) | posthog.com | - IP address<br>- Application on-time<br>- Time spent armed<br>- Video recording durations | - tracking feature usage amounts<br>- collection limited to tagged releases of Cockpit (e.g. not development branches) |

### User-Generated Events

None at this time.

## Privacy Protections

Anonymous usage data can provide valuable development insights and improvements with minimal risk or negative impact to individual users. That said, Cockpit does not require an internet connection for its basic operating features, so if you wish to avoid or obscure usage data being sent from your vehicle, you can:

1. Use a VPN service to mask your IP address, and present your vehicle as operating from somewhere else in the world
    - These services often cost money, and may slow down updates and Extension installations by reducing your network bandwidth
1. Disable [usage statistics and telemetry](../advanced/#development-troubleshooting)
1. Set up rules in your firewall and/or router to block access to specific domains
    - This will prevent using related services on connected devices, although it is generally possible to use an offline workaround
1. Completely avoid connecting your device to the internet
    - This will prevent access to all online services, so updates and installations would need to be performed manually or avoided
