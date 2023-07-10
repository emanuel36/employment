---
title: 3- Technical situations
created: '2023-04-04T13:25:22.784Z'
modified: '2023-04-04T17:48:12.237Z'
---

# 3- Technical situations

## Solved Wi-Fi issue
  * Received a desktop mode performance issue report from test team
    * Struggling
    * Low framerate
  * How wireless desktop mode works
    * P2P network
    * Phone is the host
    * Monitor is the client
  * Looking for patterns on reproduction scenarios
    * Performance decrease when Wi-Fi usage increases
    * Reproducible only when both STA and P2P were using distinct channels
  * Chipset documentation provided by the chipset vendor
    * Single antenna shared by both P2P and STA interfaces
    * Different channels usage at same time decreases throughput due to channel switch overhead
  * Adopted solution was make P2P host raise the network as same STA channel
    * Check if STA was enabled
    * Recovery the currently used channel
    * Corner case switch STA to some access point using a different channel
    * It's a scenario very rare to happen with common user
    * Business decision to not fix in order to deal with others higher priority issues
  * Funny to compare with aerospace industry

## Location system issues
  * High time to find satellites
    * Assist data download problem
    * Wrong GpsWeek
    * Antenna miscalibration
    * Lab tests executed with serial port wrongly connected to device
  * Low accuracy due to using network provider
  * Tests executed in indoor environment
