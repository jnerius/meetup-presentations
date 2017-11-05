---
layout: slide
title: Denver Developer Meetup - November 2017
description: A presentation slide for how to use reveal.js in Jekyll
theme: black
transition: slide
fragments: true
---

### Denver Developer Meetup

## IoT in ServiceNow

---

Josh Nerius

Developer Advocate

@NeriusNow

josh.nerius@servicenow.com

---

# Background

--

![IoT Infographic]({{ site.baseurl }}/assets/dev-meetup-iot/ppt_slide_1.png)

---

# The Device

- ESP8266 NodeMCU
- Arduino-compatible
- Wifi-enabled

--

![Image of Device]({{ site.baseurl }}/assets/dev-meetup-iot/device.jpg)

---

# Data Flow

--

![Animation: Device to Master Instance]({{ site.baseurl }}/assets/dev-meetup-iot/device_to_master.gif)

--

![Animation: Device to Wifi]({{ site.baseurl }}/assets/dev-meetup-iot/device_to_wifi.gif)

--

![Animation: Device to Thinger to ServiceNow]({{ site.baseurl }}/assets/dev-meetup-iot/device_to_thinger_to_servicenow.gif)

--

![Animation: ServiceNot to Thinger to Device]({{ site.baseurl}}/assets/dev-meetup-iot/servicenow_to_thinger_to_device.gif)

--

![Animation: Device Full Flow]({{ site.baseurl }}/assets/dev-meetup-iot/device_full_flow.gif)

---

# Thinger.IO

- IoT platform
- Arduino libraries
- Bi-directional communication
- Handles the hard stuff
- API endpoint per device

--- 

# Behind the Scenes

-- 

- Building 30+ devices takes a team
- Acquiring hardware
- Ordering obscure legos
- Assembling bread boards

-- 

# Pictures!

--

![]({{ site.baseurl }}/assets/dev-meetup-iot/
