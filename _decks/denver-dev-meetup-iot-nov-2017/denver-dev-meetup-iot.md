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

# IoT Environment

--

![Image of Device]({{ site.baseurl }}/assets/dev-meetup-iot/ppt_lab_env_1.png)

--

![Image of Device]({{ site.baseurl }}/assets/dev-meetup-iot/ppt_lab_env_2.png)

--

![Image of Device]({{ site.baseurl }}/assets/dev-meetup-iot/ppt_lab_env_3.png)

--

![Image of Device]({{ site.baseurl }}/assets/dev-meetup-iot/ppt_lab_env_4.png)

---

# The Device

- ESP8266 NodeMCU
- Arduino-compatible
- Wifi-enabled

--

![Image of Device]({{ site.baseurl }}/assets/dev-meetup-iot/device.jpg)

--

![Image of Device]({{ site.baseurl }}/assets/dev-meetup-iot/device_annotated.jpg)

--- 

# Hands On

---

# Data Flow

--

```c
#define ssid     "TripMateSith-BA9C"
#define password "11111111"

WiFi.begin(ssid, password);
```

![Animation: Device to Wifi]({{ site.baseurl }}/assets/dev-meetup-iot/device_to_wifi.gif)

--

```c
String url = "/api/x_snc_k17_iot_lab/logger/autoRegister";
String jsonContent = "{'MAC':'" + macAsHex + "'}\r\n";

client.print(String("POST ") + url + " HTTP/1.1\r\n" +
       "Host: " + host + "\r\n" +
       "Content-Type: application/json\r\n" +
       "Accept: text/plain\r\n" +
       "Connection: close\r\n\r\n" +
       jsonContent);
```

![Animation: Device to Master Instance]({{ site.baseurl }}/assets/dev-meetup-iot/device_to_master.gif)

--

```c
if (fuelLevel < warning_fuel_level && !alert) {
    alert = true;
    pson myMessage;
    myMessage["u_message"] = "Coolant at warning threshhold";
    myMessage["u_device_id"] = myDeviceBaseName;
    myMessage["u_sensor_reading"] = fuelLevel;
    (*thing).call_endpoint(deviceName, myMessage);
} 
```

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

- Building 30+ devices takes a team
- Acquiring hardware
- Ordering obscure legos
- Assembling bread boards

-- 

# Pictures!

--

![]({{ site.baseurl }}/assets/dev-meetup-iot/bts_box_o_components.jpg)

--

![]({{ site.baseurl }}/assets/dev-meetup-iot/bts_desk_getting_started.jpg)

--

![]({{ site.baseurl }}/assets/dev-meetup-iot/bts_incremental_progress.gif)

--

![]({{ site.baseurl }}/assets/dev-meetup-iot/bts_table_getting_started.jpg)

--

![]({{ site.baseurl }}/assets/dev-meetup-iot/bts_table_halfway_there.jpg)

--

![]({{ site.baseurl }}/assets/dev-meetup-iot/bts_a_lot_of_devices.jpg)

-- 

<iframe width="1120" height="630" src="https://www.youtube.com/embed/hmWiMtvvUTk" frameborder="0" allowfullscreen></iframe>

--- 

# Resources

- bit.ly/creatorcon-iot-blog
- github.com/jnerius/iot-device-artifacts-blog